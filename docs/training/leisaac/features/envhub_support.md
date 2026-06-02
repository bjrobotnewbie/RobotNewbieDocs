# 通过一行代码在 LeRobot 中直接加载 LeIsaac
> EnvHub：通过 HuggingFace 共享 LeIsaac 环境

[EnvHub](https://huggingface.co/docs/lerobot/envhub) 是 Hugging Face 的可复现环境中心，只需一行命令即可启动打包好的仿真，立即进行实验，并发布您自己的任务供社区使用。

LeIsaac 提供 EnvHub 支持，让您只需几个命令即可使用或分享任务。

<div style="width: 100%; max-width: 960px; margin: 0 auto;">
  <video controls preload="metadata" style="width: 100%; border-radius: 8px;">
    <source src="https://github.com/user-attachments/assets/687666f5-ebe0-421d-84a0-eb86116ac5f8" />
  </video>
</div>

## 环境设置

运行以下命令来设置您的代码环境：

```bash
# 首先参考 快速开始/安装 部分安装 leisaac
conda create -n leisaac_envhub python=3.11
conda activate leisaac_envhub

conda install -c "nvidia/label/cuda-12.8.1" cuda-toolkit
pip install -U torch==2.7.0 torchvision==0.22.0 --index-url https://download.pytorch.org/whl/cu128
pip install 'leisaac[isaaclab] @ git+https://github.com/LightwheelAI/leisaac.git#subdirectory=source/leisaac' --extra-index-url https://pypi.nvidia.com

# 安装 lerobot
pip install lerobot==0.4.1

# 固定 numpy 版本
pip install numpy==1.26.0
```

## 使用示例

EnvHub 以统一的接口公开所有 LeIsaac 支持的任务。以下示例加载 `so101_pick_orange` 并演示随机动作 rollout 和交互式遥操作。

### 随机动作

<details>
<summary><strong>envhub_random_action.py 示例代码</strong></summary>

```python
# envhub_random_action.py

import torch
from lerobot.envs.factory import make_env

# Load from the hub
envs_dict = make_env("LightwheelAI/leisaac_env:envs/so101_pick_orange.py", n_envs=1, trust_remote_code=True)

# Access the environment
suite_name = next(iter(envs_dict))
sync_vector_env = envs_dict[suite_name][0]
# retrieve the isaac environment from the sync vector env
env = sync_vector_env.envs[0].unwrapped

# Use it like any gym environment
obs, info = env.reset()

while True:
    action = torch.tensor(env.action_space.sample())
    obs, reward, terminated, truncated, info = env.step(action)
    if terminated or truncated:
        obs, info = env.reset()

env.close()
```

</details>

```bash
python envhub_random_action.py
```

您应该能看到 SO101 机械臂在纯随机命令下摆动。


### 遥操作

LeRobot 的遥操作堆栈可以驱动仿真机械臂。

连接 SO101 Leader 控制器，运行以下校准命令。

```bash
lerobot-calibrate \
    --teleop.type=so101_leader \
    --teleop.port=/dev/ttyACM0 \
    --teleop.id=leader
```

然后启动遥操作脚本。

<details>
<summary><strong>envhub_teleop_example.py 示例代码</strong></summary>

```python
# envhub_teleop_example.py

import logging
import time
import gymnasium as gym

from dataclasses import asdict, dataclass
from pprint import pformat

from lerobot.teleoperators import (  # noqa: F401
    Teleoperator,
    TeleoperatorConfig,
    make_teleoperator_from_config,
    so101_leader,
)
from lerobot.utils.robot_utils import busy_wait
from lerobot.utils.utils import init_logging
from lerobot.envs.factory import make_env


@dataclass
class TeleoperateConfig:
    teleop: TeleoperatorConfig
    env_name: str = "so101_pick_orange"
    fps: int = 60


@dataclass
class EnvWrap:
    env: gym.Env


def make_env_from_leisaac(env_name: str = "so101_pick_orange"):
    envs_dict = make_env(
        f'LightwheelAI/leisaac_env:envs/{env_name}.py',
        n_envs=1,
        trust_remote_code=True
    )
    suite_name = next(iter(envs_dict))
    sync_vector_env = envs_dict[suite_name][0]
    env = sync_vector_env.envs[0].unwrapped

    return env


def teleop_loop(teleop: Teleoperator, env: gym.Env, fps: int):
    from leisaac.devices.action_process import preprocess_device_action
    from leisaac.assets.robots.lerobot import SO101_FOLLOWER_MOTOR_LIMITS
    from leisaac.utils.env_utils import dynamic_reset_gripper_effort_limit_sim

    env_wrap = EnvWrap(env=env)

    obs, info = env.reset()
    while True:
        loop_start = time.perf_counter()
        if env.cfg.dynamic_reset_gripper_effort_limit:
            dynamic_reset_gripper_effort_limit_sim(env, 'so101leader')

        raw_action = teleop.get_action()
        processed_action = preprocess_device_action(
            dict(
                so101_leader=True,
                joint_state={
                    k.removesuffix(".pos"): v for k, v in raw_action.items()},
                motor_limits=SO101_FOLLOWER_MOTOR_LIMITS),
            env_wrap
        )
        obs, reward, terminated, truncated, info = env.step(processed_action)
        if terminated or truncated:
            obs, info = env.reset()

        dt_s = time.perf_counter() - loop_start
        busy_wait(1 / fps - dt_s)
        loop_s = time.perf_counter() - loop_start
        print(f"\ntime: {loop_s * 1e3:.2f}ms ({1 / loop_s:.0f} Hz)")


def teleoperate(cfg: TeleoperateConfig):
    init_logging()
    logging.info(pformat(asdict(cfg)))

    teleop = make_teleoperator_from_config(cfg.teleop)
    env = make_env_from_leisaac(cfg.env_name)

    teleop.connect()
    if hasattr(env, 'initialize'):
        env.initialize()
    try:
        teleop_loop(teleop=teleop, env=env, fps=cfg.fps)
    except KeyboardInterrupt:
        pass
    finally:
        teleop.disconnect()
        env.close()


def main():
    teleoperate(TeleoperateConfig(
        teleop=so101_leader.SO101LeaderConfig(
            port="/dev/ttyACM0",
            id='leader',
            use_degrees=False,
        ),
        env_name="so101_pick_orange",
        fps=60,
    ))


if __name__ == "__main__":
    main()

```

</details>

```bash
python envhub_teleop_example.py
```

运行此脚本可以让您使用物理 Leader 设备操作仿真机械臂。

## 补充说明

我们保持 EnvHub 覆盖范围与 LeIsaac 任务同步。目前支持：
- `so101_pick_orange`
- `so101_lift_cube`
- `so101_clean_toytable`
- `bi_so101_fold_cloth`

参考[此处](../resources/available_env.md)查看我们可用的环境。

通过在调用 `make_env` 时指定不同的脚本来切换任务，例如：

```python
envs_dict_pick_orange = make_env("LightwheelAI/leisaac_env:envs/so101_pick_orange.py", n_envs=1, trust_remote_code=True)
envs_dict_lift_cube = make_env("LightwheelAI/leisaac_env:envs/so101_lift_cube.py", n_envs=1, trust_remote_code=True)
envs_dict_clean_toytable = make_env("LightwheelAI/leisaac_env:envs/so101_clean_toytable.py", n_envs=1, trust_remote_code=True)
envs_dict_fold_cloth = make_env("LightwheelAI/leisaac_env:envs/bi_so101_fold_cloth.py", n_envs=1, trust_remote_code=True)
```

::::info
注意：使用 `bi_so101_fold_cloth` 时，在获取环境后立即调用 `initialize()`，然后再执行其他操作：

```python
import torch
from lerobot.envs.factory import make_env

# Load from the hub
envs_dict = make_env("LightwheelAI/leisaac_env:envs/bi_so101_fold_cloth.py", n_envs=1, trust_remote_code=True)

# Access the environment
suite_name = next(iter(envs_dict))
sync_vector_env = envs_dict[suite_name][0]
# retrieve the isaac environment from the sync vector env
env = sync_vector_env.envs[0].unwrapped

# NOTE: initialize() first
env.initialize()

# other operation with env...
```
::::
