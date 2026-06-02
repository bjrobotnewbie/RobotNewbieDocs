# 遥操作

## 遥操作脚本

您可以使用以下脚本运行遥操作任务。查看更多支持的遥操作任务请参考[此处](../resources/available_env.md)。

```shell
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=so101leader \
    --port=/dev/ttyACM0 \
    --num_envs=1 \
    --device=cuda \
    --enable_cameras \
    --record \
    --dataset_file=./datasets/dataset.hdf5
```

<details>
<summary><strong>teleop_se3_agent.py 参数说明</strong></summary>

- `--task`：指定要运行的任务环境名称，例如 `LeIsaac-SO101-PickOrange-v0`。

- `--seed`：指定环境的随机种子，例如 `42`。

- `--teleop_device`：指定遥操作设备类型，例如 `so101leader`、`bi-so101leader`、`keyboard`、`gamepad`、`lekiwi-leader`、`lekiwi-keyboard`、`lekiwi-gamepad`。

-  `--port`：指定遥操作设备的端口，例如 `/dev/ttyACM0`。仅在 teleop_device 为 `so101leader` 和 `lekiwi-leader` 时使用。

- `--remote_endpoint`：远程 so101leader 的 ZMQ 端点（例如 `tcp://192.168.1.10:5556`）。设置后，将连接到在带有 leader 机械臂的机器上运行的 `so101_joint_state_server.py`。参见下面的 [远程遥操作](#remote-teleoperation)。

- `--left_arm_port`：指定左臂的端口，例如 `/dev/ttyACM0`。仅在 teleop_device 为 `bi-so101leader` 时使用。

- `--right_arm_port`：指定右臂的端口，例如 `/dev/ttyACM1`。仅在 teleop_device 为 `bi-so101leader` 时使用。

- `--num_envs`：设置并行仿真环境的数量，遥操作时通常为 `1`。

- `--device`：指定计算设备，如 `cpu` 或 `cuda`（GPU）。

- `--enable_cameras`：启用相机传感器以在遥操作过程中收集视觉数据。

- `--record`：启用数据录制；将遥操作数据保存到 HDF5 文件。

- `--dataset_file`：保存录制数据集的路径，例如 `./datasets/record_data.hdf5`。

- `--resume`：启用从现有数据集文件恢复数据录制。

- `--recalibrate`：重新校准 SO101-Leader 或 Bi-SO101Leader。

- `--quality`：是否启用高质量渲染模式。

- `--use_lerobot_recorder`：是否使用 lerobot 录制器。

- `--lerobot_dataset_repo_id`：LeRobot 数据集仓库 ID。

- `--lerobot_dataset_fps`：LeRobot 数据集每秒帧数。

</details>

::::tip
我们支持多种设备进行遥操作。查看更多设备和用法说明请参考[此处](../resources/available_devices.md)。
::::

## 远程遥操作

当 leader 机械臂连接到与运行 Isaac Sim 的机器不同的机器时
（例如，Isaac Sim 在云 GPU 实例上，leader 机械臂在您的笔记本电脑上），您可以使用
通过 ZMQ 的**远程遥操作**。

### 工作原理

leader 机械臂机器运行一个轻量级发布器，读取电机位置并通过网络流式传输。Isaac Sim 机器订阅并使用关节状态进行遥操作——无需 USB 转发。

```
Laptop (leader arm)                      Cloud GPU (Isaac Sim)
┌──────────────────────────┐  ZMQ PUB/SUB  ┌──────────────────────┐
│ so101_joint_state_server │──────────────►│ SO101LeaderRemote    │
│ reads motors             │   tcp:5556    │ teleop_se3_agent.py  │
│ at 50 Hz                 │               │ --remote_endpoint    │
└──────────────────────────┘               └──────────────────────┘
```

### 先决条件

- 两台机器之间的网络连接（直接或通过 SSH 隧道）
- 在 Isaac Sim 机器上安装 `pyzmq`：`pip install "source/leisaac[remote]"` 或 `pip install pyzmq`

### 本地机器设置

在连接 leader 机械臂的机器上，安装带远程支持的 leisaac：

```bash
pip install "source/leisaac[remote]"
```

::::info
在远程机器（Isaac Sim 机器）上，您需要安装完整的仿真堆栈，包括 PyTorch、Isaac Sim 和 IsaacLab。在您的本地机器上，您可以跳过这些重量级依赖项——只需运行上面的命令；不需要在本地安装 PyTorch/Isaac Sim/IsaacLab。
::::

### 使用方法

**终端 1 — 本地机器（leader 机械臂）：**

```bash
python scripts/environments/teleoperation/so101_joint_state_server.py \
    --port /dev/ttyACM0 --id leader_arm --rate 50
```

如果不存在校准文件，脚本将自动运行交互式校准过程。要强制重新校准，请添加 `--recalibrate`。

**终端 2 — 远程机器（Isaac Sim）：**

```bash
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=so101leader \
    --remote_endpoint=tcp://<local-machine-ip>:5556 \
    --num_envs=1 --device=cuda --enable_cameras
```

### SSH 反向端口转发

如果云实例无法直接访问您的笔记本电脑（例如，位于 NAT 或防火墙后面），
使用 SSH 反向端口转发在远程机器上暴露发布器的端口：

```bash
# 在您的笔记本电脑上 — 将本地端口 5556 转发到远程机器的 localhost:5556
ssh -R 5556:localhost:5556 ubuntu@<cloud-instance-ip>
```

然后在远程机器上，连接到 `localhost` 而不是您笔记本电脑的 IP：

```bash
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=so101leader \
    --remote_endpoint=tcp://localhost:5556 \
    --num_envs=1 --device=cuda --enable_cameras
```

### 参数说明

- `--remote_endpoint`：要订阅的 ZMQ 端点（例如 `tcp://192.168.1.10:5556`
  或通过 SSH 隧道的 `tcp://localhost:5556`）。设置后，使用 `SO101LeaderRemote` 而不是
  本地的 `SO101Leader`。

- `--id`（发布器）：校准 ID（默认：`leader_arm`）。校准存储在
  `scripts/environments/teleoperation/.cache/{id}.json` 中。

- `--rate`（发布器）：电机读取频率，单位为 Hz（默认：50）。30–50 Hz 对于
  LeIsaac 遥操作来说已经足够。

- `--recalibrate`（发布器）：即使存在校准文件也强制重新校准。

## 操作说明

如果指定的缓存路径下不存在校准文件，或者您使用 `--recalibrate` 启动，系统将提示您校准 SO101Leader。请参考[文档](https://huggingface.co/docs/lerobot/so101#calibration-video)了解校准步骤。

进入 IsaacLab 窗口后，按键盘上的 `b` 键开始遥操作。然后您可以使用指定的 teleop_device 控制仿真中的机器人。如果需要在完成操作后重置环境，只需按 `r` 或 `n` 键。`r` 表示重置环境并将任务标记为失败，而 `n` 表示重置环境并将任务标记为成功。

如果遇到权限错误（如 `ConnectionError`），可以使用以下命令临时授予权限：
```bash
sudo chmod 666 /dev/ttyACM0
```

或者，您可以将当前用户添加到 dialout 组；您需要重启设备才能生效：
```bash
sudo usermod -aG dialout $USER
```
