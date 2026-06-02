# LeIsaac × Cosmos：视频到动作数据生成流水线

本教程通过集成 **[Cosmos-Predict2.5](https://github.com/nvidia-cosmos/cosmos-predict2.5)** 和 **[GR00T-Dreams IDM](https://github.com/nvidia/GR00T-dreams)** 到 LeIsaac 原生的数据生成循环中，扩展了 **[LeIsaac](https://github.com/LightwheelAI/leisaac)**。**LeIsaac** 用于收集遥操作演示（HDF5）并将其转换为 LeRobot 数据集。**Cosmos-Predict 2.5** 在这些视频上进行后训练以大规模合成额外的 rollout 视频，而 **IDM** 在同一数据集上进行微调以从生成的视频中推断机器人动作。Together，这产生了 **一个可扩展的流水线，用于构建合成的、完整的 LeRobot 数据集** ，可以直接在 **LeIsaac** 中回放和评估。

## 🎥 从单个演示到通过 Cosmos 的大规模合成 Rollout
<div align="center">
  <video src="https://github.com/user-attachments/assets/f0820382-d525-4007-90bc-04c0ceb2a5fc"
         controls
         width="100%">
  </video>
</div>

## 概述

1. 使用 **LeIsaac** 收集 **HDF5 数据集** 并将其转换为 **LeRobot 数据集**
2. 后训练 **Cosmos-Predict2.5**，然后运行推理以 **生成合成视频**
3. 微调 **IDM**，然后运行推理以 **生成合成 LeRobot 轨迹（parquet）**
4. 将 **原始 HDF5 数据集** 和 **IDM 生成的 LeRobot 轨迹（parquet）** 转换为 **可回放的 LeIsaac HDF5 数据集** 并使用 **LeIsaac** **回放和评估**


## 步骤 1：使用 LeIsaac 进行数据收集

::::tip[此步骤您将得到]
- **HDF5** 格式的真实演示数据集（通过 LeIsaac 遥操作在 Isaac Sim 中录制）
- 转换为 **LeRobot** 格式的数据集（视频 + 元数据 + parquet）
::::

### 1.1 通过 LeIsaac 遥操作收集 HDF5 数据集

首先，使用 **LeIsaac** 遥操作收集演示。

- 参考：**[遥操作 | LeIsaac 文档](https://lightwheelai.github.io/leisaac/docs/getting_started/teleoperation)**
- 输出：一个 HDF5 文件（例如 `dataset.hdf5`）

HDF5 数据集作为回放和评估的主要真实来源。

它也是用于为 Cosmos 和 IDM 构建初始 **LeRobot 数据集** 的来源。

### 1.2 将 HDF5 转换为 LeRobot 数据集

将录制的 HDF5 数据集转换为 **LeRobot 格式**。

- 参考：**[数据约定 | LeIsaac 文档](https://lightwheelai.github.io/leisaac/docs/getting_started/policy_support#1-data-convention)**
- 输出：用于后训练 **Cosmos-Predict2.5** 和微调 **IDM** 的 LeRobot 数据集

::::info
**💡重要（视频编码）**

确保所有输出视频都使用 **H.264 (h264)** 编码。

避免使用 **AV1** 编码，因为 Cosmos 和 IDM 可能在解码或处理过程中失败。

您可以直接修改 `leisaac/scripts/convert/isaaclab2lerobot.py` 以确保正确的视频编码：

```diff
- "video.codec": "av1"
+ "video.codec": "h264"
```

::::

## 步骤 2：使用 Cosmos-predict2.5 生成视频

::::tip[此步骤您将得到]
- 在您的任务特定 LeRobot 视频上后训练的 **Cosmos-Predict2.5 检查点**
- 由 Cosmos 生成的一组 **合成 rollout 视频**

在此流水线中，**Cosmos-Predict 2.5** 纯粹用作 **视频生成器**。

它从通过 **LeIsaac** 收集的 LeRobot 视频中学习视觉 rollout 分布，并根据以下条件生成新的 rollout 视频：
- 文本提示（任务描述），
- 以及示例视频的前几帧。

这些生成的视频稍后将使用 **IDM** 转换为可执行的机器人动作。
::::

### 2.1 安装 Cosmos-Predict2.5

按照官方安装指南设置 Cosmos-Predict2.5 环境：**[设置 Cosmos-Predict2.5](https://github.com/nvidia-cosmos/cosmos-predict2.5/blob/main/docs/setup.md)**


### 2.2 准备 Cosmos-Predict2.5 后训练数据集（视频 + 提示）

数据集文件夹格式应为：
```text
cosmos-predict2.5/datasets/benchmark_train/<task_name>/
├── metas/
│   ├── *.txt
├── videos/
│   ├── *.mp4
```
从您的 LeRobot 数据集构建它：

1. 将 MP4 视频从 LeRobot 数据集的 `<path_to_lerobot_dataset>/videos/` 复制到 `cosmos-predict2.5/datasets/benchmark_train/<task_name>/videos/`

2. 将复制的视频重命名为干净的数字序列：`1.mp4`、`2.mp4`、`3.mp4`、...

3. 在 `cosmos-predict2.5/datasets/benchmark_train/<task_name>/metas/` 下创建相同数量的提示文件

4. 使用 `<path_to_lerobot_dataset>/meta/tasks.jsonl` 中的任务文本填充每个提示文件。例如，如果 tasks.jsonl 中的一行是 `{"task_index": 0, "task": "Lift the red cube up."}`，那么 1.txt 应包含 `Lift_the_red_cube_up`。在许多单任务情况下，您会将相同的提示写入所有 *.txt 文件，但该格式支持每个视频的提示（如果需要）。

### 2.3 后训练 Cosmos-Predict2.5

按照 **[官方后训练说明](https://github.com/nvidia-cosmos/cosmos-predict2.5/blob/main/docs/post-training_video2world_gr00t.md#21-post-training-cosmos-predict25-2b-model)** 在准备好的数据集上后训练 Cosmos-Predict2.5。

此步骤产生一个专门针对您的机器人体现和任务分布的 Cosmos-Predict2.5 检查点。

### 2.4 运行推理以生成视频

后训练后，Cosmos-Predict2.5 模型检查点通常以 **分布式检查点 (DCP)** 格式保存。在运行推理之前，需要将这些检查点转换为推理脚本可以加载的 **整合 PyTorch 格式**。

**按照 [将 DCP 检查点转换为整合 PyTorch 格式](https://github.com/nvidia-cosmos/cosmos-predict2.5/blob/main/docs/post-training_video2world_gr00t.md#31-converting-dcp-checkpoint-to-consolidated-pytorch-format) 转换 DCP 检查点**。

转换检查点后，按照 [官方运行推理说明](https://github.com/nvidia-cosmos/cosmos-predict2.5/blob/main/docs/post-training_video2world_gr00t.md#32-running-inference) 运行视频生成分推理。

🔬 **批量推理（用于微调 IDM）**

对于大规模视频生成，支持批量推理。
在 `cosmos-predict2.5/scripts/` 下创建批量推理助手脚本 `generate_batch_config.py`。

<details>
<summary><strong>cosmos-predict2.5/scripts/generate_batch_config.py</strong></summary>

```python
#!/usr/bin/env python3
"""
生成批量推理配置文件 (JSONL)。

此脚本扫描输入视频目录并生成一个 JSONL 文件
用于批量 video2world 推理。每行对应一个视频。
可以选择从 episodes.jsonl 加载任务提示。
"""

import json
import os
from pathlib import Path

# ---------------------------------------------------------------------
# 配置
# ---------------------------------------------------------------------

# 用于生成推理配置的输入视频目录
VIDEO_DIR = "<path_to_lerobot_dataset>/videos/chunk-000/observation.images.front"

# 元数据目录（用于加载文本提示时）
META_DIR = "<path_to_lerobot_dataset>/meta"

# 输出 JSONL 文件
OUTPUT_JSONL = "batch_inference_config.jsonl"

# 任务名称前缀
TASK_NAME = "liftcube"

# ---------------------------------------------------------------------
# 所有视频共享的基础配置模板
# ---------------------------------------------------------------------

BASE_CONFIG = {
    "inference_type": "video2world",
    "seed": 21,
    "guidance": 7,
    "resolution": "480,640",
    "enable_autoregressive": True,
    # 输出帧数（例如 110 ≈ 6秒，140 ≈ 8秒，210 ≈ 16秒）
    "num_output_frames": 210,
    "chunk_size": 77,
    "chunk_overlap": 1,
    # 默认提示（如果找到特定于剧集的提示，将被覆盖）
    "prompt": "The robot arm is performing a task",
    "negative_prompt": (
        "The video captures a series of frames showing ugly scenes, static with no motion, "
        "motion blur, over-saturation, shaky footage, low resolution, grainy texture, "
        "pixelated images, poorly lit areas, underexposed and overexposed scenes, "
        "poor color balance, washed out colors, choppy sequences, jerky movements, "
        "low frame rate, artifacting, color banding, unnatural transitions, "
        "outdated special effects, fake elements, unconvincing visuals, "
        "poorly edited content, jump cuts, visual noise, and flickering. "
        "Overall, the video is of poor quality."
    ),
}

# ---------------------------------------------------------------------
# 主逻辑
# ---------------------------------------------------------------------

def main(use_prompt=True):
    video_dir = Path(VIDEO_DIR)
    meta_dir = Path(META_DIR)

    # 收集所有 mp4 视频文件
    video_files = sorted(video_dir.glob("*.mp4"))
    print(f"Found {len(video_files)} video files")

    # 如果启用，从 episodes.jsonl 加载提示
    episode_prompts = {}
    if use_prompt:
        episodes_file = meta_dir / "episodes.jsonl"
        if episodes_file.exists():
            with open(episodes_file, 'r') as f:
                for line in f:
                    episode_data = json.loads(line)
                    episode_index = episode_data.get("episode_index")
                    tasks = episode_data.get("tasks", [])
                    if episode_index is not None and tasks:
                        # 使用第一个任务作为剧集提示
                        prompt = f"The robot arm is performing a task. {tasks[0]}"
                        episode_prompts[episode_index] = prompt
            print(f"✓ Loaded {len(episode_prompts)} prompts from episodes.jsonl")

    # 生成 JSONL 配置文件
    with open(OUTPUT_JSONL, 'w') as f:
        for video_file in video_files:
            # 不带扩展名的视频文件名（例如 episode_000001）
            video_name = video_file.stem

            # 基于基础模板创建每个视频的配置
            config = BASE_CONFIG.copy()
            config["name"] = f"{TASK_NAME}_{video_name}"
            config["input_path"] = str(video_file)

            # 如果可用，分配特定于剧集的提示
            if use_prompt:
                # 从视频文件名中提取剧集索引
                episode_index = int(video_name.split('_')[-1])
                if episode_index in episode_prompts:
                    config["prompt"] = episode_prompts[episode_index]

            # 每行写入一个 JSON 对象
            f.write(json.dumps(config) + '\n')

    # 摘要信息
    print(f"✓ Config file generated: {OUTPUT_JSONL}")
    print(f"  - Total videos: {len(video_files)}")
    print(f"  - Use prompts: {'Yes' if use_prompt else 'No'}")
    if use_prompt:
        print(
            f"  - Videos with matched prompts: "
            f"{sum(1 for vf in video_files if int(vf.stem.split('_')[-1]) in episode_prompts)}"
        )

# ---------------------------------------------------------------------
# 脚本入口点
# ---------------------------------------------------------------------

if __name__ == "__main__":
    import sys
    # 仅在提供 '--use-prompt' 时启用文本提示
    use_prompt = "--use-prompt" in sys.argv
    main(use_prompt=use_prompt)

```

</details>

您可以使用以下命令生成批量推理配置 `jsonl` 文件：
```bash
# 从 cosmos-predict2.5 项目根目录运行此命令
# cd <path_to_cosmos-predict2.5>
python scripts/generate_batch_config.py --use-prompt
```

## 步骤 3：使用 IDM 进行动作推理

::::tip[此步骤您将得到]
- 在您的 LeRobot 数据集和机器人体现上微调的 **IDM 检查点**
- 从 Cosmos 生成的视频中推断出的一组 **LeRobot 格式轨迹**（例如 parquet 文件）

在此流水线中，来自 **GR00T-Dreams** 的 **IDM（逆动力学模型）** 用于将 **Cosmos 生成的 rollout 视频** 转换为可执行的机器人动作。

IDM 首先在通过 **LeIsaac** 收集的原始 LeRobot 数据集上进行微调，然后应用于从合成视频中推断动作，生成一个新的、完全兼容的 **LeRobot 数据集**。
::::

### 3.1 安装 IDM 环境

IDM 需要 **Cosmos-Predict2** 环境（**不是 2.5**）。

按照官方先决条件指南：**[Cosmos-Predict2 – 先决条件](https://github.com/nvidia-cosmos/cosmos-predict2/blob/main/documentations/post-training_video2world_gr00t.md#prerequisites)**

💡 **依赖安装说明**
- 安装 `openai` 和 `tyro` 等依赖项时，使用：
  ```bash
  uv pip install openai tyro numpydantic albumentations tianshou
  ```
- 对于 `pytorch3d`，使用 `no build isolation` 安装：
  ```bash
  uv pip install --no-build-isolation git+https://github.com/facebookresearch/pytorch3d.git
  ```
- 如果遇到与 `APEX` 相关的问题，可以安全地从 uv 环境中移除它。APEX 对于 IDM 训练或推理不是必需的。:

### 3.2 微调 IDM
对于 IDM 微调，请参考 **[训练自定义 IDM 模型](https://github.com/NVIDIA/GR00T-Dreams?tab=readme-ov-file#optional-33-training-custom-idm-model)**

#### 3.2.1 准备：模态元数据和 DataConfig

**1.添加 modality.json**
在 `GR00T-Dreams/IDM_dump/global_metadata/{embodiment_name}/` 下创建 `modality.json` 并将同一文件复制到 `<path_to_lerobot_dataset>/meta/`

<details>
<summary><strong>示例：SO101 modality.json</strong></summary>

```json
{
  "state": {
    "shoulder_pan": { "start": 0, "end": 1 },
    "shoulder_lift": { "start": 1, "end": 2 },
    "elbow_flex": { "start": 2, "end": 3 },
    "wrist_flex": { "start": 3, "end": 4 },
    "wrist_roll": { "start": 4, "end": 5 },
    "gripper": { "start": 5, "end": 6 }
  },
  "action": {
    "shoulder_pan": { "start": 0, "end": 1, "absolute": false },
    "shoulder_lift": { "start": 1, "end": 2, "absolute": false },
    "elbow_flex": { "start": 2, "end": 3, "absolute": false },
    "wrist_flex": { "start": 3, "end": 4, "absolute": false },
    "wrist_roll": { "start": 4, "end": 5, "absolute": false },
    "gripper": { "start": 5, "end": 6, "absolute": false }
  },
  "video": {
    "front": { "original_key": "observation.images.front" }
  },
  "annotation": {
    "human.task_description": { "original_key": "task_index" }
  }
}
```
</details>

**2.添加新的 DataConfig (So101DataConfig)**
在 `GR00T-Dreams/gr00t/experiment/data_config_idm.py` 中添加定义的新 `So101DataConfig` 类：

<details>
<summary><strong>GR00T-Dreams/gr00t/experiment/data_config_idm.py</strong></summary>

```python
class So101DataConfig(BaseDataConfig):
    video_keys = ["video.front"]
    state_keys = ["state.shoulder_pan", "state.shoulder_lift", "state.elbow_flex", "state.wrist_flex", "state.wrist_roll", "state.gripper"]
    action_keys = ["action.shoulder_pan", "action.shoulder_lift", "action.elbow_flex", "action.wrist_flex", "action.wrist_roll", "action.gripper"]
    language_keys = ["annotation.human.task_description"]
    observation_indices = [0, 16]
    action_indices = list(range(16))

    def modality_config(self) -> dict[str, ModalityConfig]:
        video_modality = ModalityConfig(
            delta_indices=self.observation_indices,
            modality_keys=self.video_keys,
        )

        state_modality = ModalityConfig(
            delta_indices=self.observation_indices,
            modality_keys=self.state_keys,
        )

        action_modality = ModalityConfig(
            delta_indices=self.action_indices,
            modality_keys=self.action_keys,
        )

        language_modality = ModalityConfig(
            delta_indices=self.observation_indices,
            modality_keys=self.language_keys,
        )

        modality_configs = {
            "video": video_modality,
            "state": state_modality,
            "action": action_modality,
            "language": language_modality,
        }

        return modality_configs

    def transform(self) -> ModalityTransform:
        transforms = [
            # 视频变换
            VideoToTensor(apply_to=self.video_keys),
            VideoCrop(apply_to=self.video_keys, scale=0.95),
            VideoResize(apply_to=self.video_keys, height=224, width=224, interpolation="linear"),
            VideoColorJitter(
                apply_to=self.video_keys,
                brightness=0.3,
                contrast=0.4,
                saturation=0.5,
                hue=0.08,
            ),
            VideoToNumpy(apply_to=self.video_keys),
            # 状态变换
            StateActionToTensor(apply_to=self.state_keys),
            StateActionTransform(
                apply_to=self.state_keys,
                normalization_modes={key: "min_max" for key in self.state_keys},
            ),
            # 动作变换
            StateActionToTensor(apply_to=self.action_keys),
            StateActionTransform(
                apply_to=self.action_keys,
                normalization_modes={key: "min_max" for key in self.action_keys},
            ),
            # 连接变换
            ConcatTransform(
                video_concat_order=self.video_keys,
                state_concat_order=self.state_keys,
                action_concat_order=self.action_keys,
            ),
            # 模型特定变换
            GR00TIDMTransform(
                state_horizon=len(self.observation_indices),
                action_horizon=len(self.action_indices),
                max_state_dim=64,
                max_action_dim=32,
            ),
        ]
        return ComposedModalityTransform(transforms=transforms)
```

在 `DATA_CONFIG_MAP` 中注册新配置：
```python
DATA_CONFIG_MAP = {
    "gr1_arms_waist": Gr1ArmsWaistDataConfig(),
    "gr1_arms_only": Gr1ArmsOnlyDataConfig(),
    "gr1_full_upper_body": Gr1FullUpperBodyDataConfig(),
    "bimanual_panda_gripper": BimanualPandaGripperDataConfig(),
    "bimanual_panda_hand": BimanualPandaHandDataConfig(),
    "single_panda_gripper": SinglePandaGripperDataConfig(),
    "so100": So100DataConfig(),
    "franka": FrankaDataConfig(),
    "so101": So101DataConfig(),#add
}
```
</details>

#### 3.2.2 运行 IDM 后训练

使用 LeRobot 数据集和新注册的数据配置后训练 **IDM (GR00T-Dreams)**。

```bash
PYTHONPATH=. torchrun scripts/idm_training.py \
  --dataset-path <path_to_lerobot_dataset> \
  --data-config <key_from_DATA_CONFIG_MAP> \
  --output_dir <path_to_output_dir>
```

加载数据集后，`stats.json` 将自动生成在 `<path_to_lerobot_dataset>/meta/` 下。

**将此文件复制到 `GR00T-Dreams/IDM_dump/global_metadata/{embodiment_name}/`。**

### 3.3 提取机器人动作到 LeRobot 格式

IDM 后训练后，使用训练好的模型从 Cosmos 生成的视频中推断动作。

#### 3.3.1 准备推理配置

选择一个检查点目录（例如 checkpoint-10000/）并创建 `checkpoint-10000/experiment_cfg/conf.yaml`：

<details>
<summary><strong>checkpoint-10000/experiment_cfg/conf.yaml</strong></summary>

```yaml
# Configuration for so101 IDM (LiftCube dataset)
# SO101 robot with 6 DOF: shoulder_pan, shoulder_lift, elbow_flex, wrist_flex, wrist_roll, gripper

modality_configs:
  so101:
    video:
      _target_: gr00t.data.dataset.ModalityConfig
      delta_indices:
      - 0
      - 16
      modality_keys:
      - video.front
    state:
      _target_: gr00t.data.dataset.ModalityConfig
      delta_indices:
      - 0
      - 16
      modality_keys:
      - state.shoulder_pan
      - state.shoulder_lift
      - state.elbow_flex
      - state.wrist_flex
      - state.wrist_roll
      - state.gripper
    action:
      _target_: gr00t.data.dataset.ModalityConfig
      delta_indices:
      - 0
      - 1
      - 2
      - 3
      - 4
      - 5
      - 6
      - 7
      - 8
      - 9
      - 10
      - 11
      - 12
      - 13
      - 14
      - 15
      modality_keys:
      - action.shoulder_pan
      - action.shoulder_lift
      - action.elbow_flex
      - action.wrist_flex
      - action.wrist_roll
      - action.gripper
    language:
      _target_: gr00t.data.dataset.ModalityConfig
      delta_indices:
      - 0
      modality_keys:
      - annotation.human.task_description

all_transforms:
  so101:
    _target_: gr00t.data.transform.base.ComposedModalityTransform
    transforms:
    - _target_: gr00t.data.transform.video.VideoToTensor
      apply_to:
      - video.front
    - _target_: gr00t.data.transform.video.VideoCrop
      apply_to:
      - video.front
      scale: 0.95
    - _target_: gr00t.data.transform.video.VideoResize
      apply_to:
      - video.front
      height: 224
      width: 224
      interpolation: linear
    - _target_: gr00t.data.transform.video.VideoColorJitter
      apply_to:
      - video.front
      brightness: 0.3
      contrast: 0.4
      saturation: 0.5
      hue: 0.08
    - _target_: gr00t.data.transform.video.VideoToNumpy
      apply_to:
      - video.front
    - _target_: gr00t.data.transform.state_action.StateActionToTensor
      apply_to:
      - state.shoulder_pan
      - state.shoulder_lift
      - state.elbow_flex
      - state.wrist_flex
      - state.wrist_roll
      - state.gripper
    - _target_: gr00t.data.transform.state_action.StateActionTransform
      apply_to:
      - state.shoulder_pan
      - state.shoulder_lift
      - state.elbow_flex
      - state.wrist_flex
      - state.wrist_roll
      - state.gripper
      normalization_modes:
        state.shoulder_pan: min_max
        state.shoulder_lift: min_max
        state.elbow_flex: min_max
        state.wrist_flex: min_max
        state.wrist_roll: min_max
        state.gripper: min_max
    - _target_: gr00t.data.transform.state_action.StateActionToTensor
      apply_to:
      - action.shoulder_pan
      - action.shoulder_lift
      - action.elbow_flex
      - action.wrist_flex
      - action.wrist_roll
      - action.gripper
    - _target_: gr00t.data.transform.state_action.StateActionTransform
      apply_to:
      - action.shoulder_pan
      - action.shoulder_lift
      - action.elbow_flex
      - action.wrist_flex
      - action.wrist_roll
      - action.gripper
      normalization_modes:
        action.shoulder_pan: min_max
        action.shoulder_lift: min_max
        action.elbow_flex: min_max
        action.wrist_flex: min_max
        action.wrist_roll: min_max
        action.gripper: min_max
    - _target_: gr00t.data.transform.concat.ConcatTransform
      video_concat_order:
      - video.front
      state_concat_order:
      - state.shoulder_pan
      - state.shoulder_lift
      - state.elbow_flex
      - state.wrist_flex
      - state.wrist_roll
      - state.gripper
      action_concat_order:
      - action.shoulder_pan
      - action.shoulder_lift
      - action.elbow_flex
      - action.wrist_flex
      - action.wrist_roll
      - action.gripper
    - _target_: gr00t.model.transforms_idm.GR00TIDMTransform
      state_horizon: 2
      action_horizon: 16
      max_state_dim: 64
      max_action_dim: 32

metadata_versions:
  so101: v2.1
```

</details>

使用与 SO101 模态定义和变换匹配的配置（如上所示）。

#### 3.3.2 运行 IDM 推理

**1.修改转换脚本以添加特定的体现（SO101）**
为了支持 SO101 体现，我们扩展了 `GR00T-Dreams/IDM_dump/` 下的转换工具以处理 **SO101 特定的** 视频流和元数据。

<details>
<summary><strong>GR00T-DreamsIDM_dump/preprocess_video.py</strong></summary>

```diff
+    # === [1/3] 视频帧写入：添加 SO101 输出键（前视图） ===
     elif dataset == 'so100':
         image = resize_with_padding(frame, ratio)
         output_videos['observation.images.webcam'].append_data(image)
+    elif dataset == 'so101':
+        image = resize_with_padding(frame, ratio)
+        output_videos['observation.images.front'].append_data(image)
     else:
         raise ValueError(f"Unknown task: {src_path}")

     ----------------------------------------------------------------------

+    # === [2/3] 输出目录映射：为 SO101 添加 videos/observation.images.front ===
     elif dataset == 'so100':
         output_dirs = {
             'observation.images.webcam': os.path.join(dst_dir, 'videos', 'observation.images.webcam'),
         }
+    elif dataset == 'so101':
+        output_dirs = {
+            'observation.images.front': os.path.join(dst_dir, 'videos', 'observation.images.front'),
+        }

     for dir_path in output_dirs.values():
         os.makedirs(dir_path, exist_ok=True)

     ----------------------------------------------------------------------

+    # === [3/3] CLI 参数：将 so101 添加到数据集选项中 ===
     parser.add_argument('--max_videos', type=int, default=None,
                         help='Maximum number of videos to process per subdirectory (for debugging)')
-    parser.add_argument('--dataset', type=str, default='robocasa',
-                        help='Dataset name', choices=['robocasa', 'gr1', 'franka', 'so100'])
+    parser.add_argument('--dataset', type=str, default='robocasa',
+                        help='Dataset name', choices=['robocasa', 'gr1', 'franka', 'so100', 'so101'])

     parser.add_argument("--recursive", action="store_true", help="Process subdirectories recursively, maintaining directory structure")
```
</details>

<details>
<summary><strong>GR00T-DreamsIDM_dump/raw_to_lerobot.py</strong></summary>

```diff
+    # === [1/2] 体现推断和注释源：添加 SO101 ===
     if args.embodiment is None:
         if 'robocasa' in args.output_dir:
             args.embodiment = "robocasa_panda_omron"
         elif 'gr1' in args.output_dir:
             args.embodiment = "gr1_unified"
         elif 'franka' in args.output_dir:
             args.embodiment = "franka"
         elif 'so100' in args.output_dir:
             args.embodiment = "so100"
+        elif 'so101' in args.output_dir:
+            args.embodiment = "so101"
         else:
             raise ValueError(f"Unknown embodiment for {args.output_dir}")

     if args.embodiment == "robocasa_panda_omron":
         args.annotation_source = "human.action.task_description"
     elif args.embodiment == "gr1_unified":
         args.annotation_source = "human.coarse_action"
     elif args.embodiment == "franka":
         args.annotation_source = "language.language_instruction"
     elif args.embodiment == "so100":
         args.annotation_source = "human.task_description"
+    elif args.embodiment == "so101":
+        args.annotation_source = "human.task_description"

     ----------------------------------------------------------------------

+    # === [2/2] 全局元数据源：添加 SO101 模态定义 ===
     elif args.embodiment == "so100":
         source_dir = "IDM_dump/global_metadata/so100"
+    elif args.embodiment == "so101":
+        source_dir = "IDM_dump/global_metadata/so101"

     # copy modality.json
     shutil.copy(
         source_dir + "/modality.json",
         args.output_dir + "/meta/modality.json"
     )
```
</details>

<details>
<summary><strong>GR00T-DreamsIDM_dump/dump_idm_actions.py</strong></summary>

```diff
+    # === [1/1] 体标签映射：添加 SO101 ===
     if "gr1" in embodiment:
         embodiment_tag = EmbodimentTag.GR1_unified
     elif "franka" in embodiment:
         embodiment_tag = EmbodimentTag.FRANKA
     elif "so100" in embodiment:
         embodiment_tag = EmbodimentTag.SO100
+    elif "so101" in embodiment:
+        embodiment_tag = EmbodimentTag.NEW_EMBODIMENT
     elif "robocasa" in embodiment:
         embodiment_tag = EmbodimentTag.ROBOCASA
     else:
         raise ValueError(f"Unknown embodiment: {embodiment}")
```
</details>


**2.创建从 Cosmos 到 IDM 的格式转换接口**
在 `GR00T-Dreams/IDM_dump/` 下创建转换助手脚本 `cosmos2.5_to_step2_format.py`。
<details>
<summary><strong>GR00T-Dreams/IDM_dump/cosmos2.5_to_step2_format.py</strong></summary>

```python
#!/usr/bin/env python3
"""
将 cosmos2.5 输出（+可选的 LeRobot 元数据）转换为 convert_directory 输出格式。

输入：
  cosmos_dir/
    ├── *.mp4
    ├── *.json（与 mp4 相同的词干）
    └── ...

可选：
  lerobot_dir/
    └── meta/
        ├── tasks.jsonl
        └── episodes.jsonl

输出：
  output_dir/
    ├── <TaskName>/
    │   ├── 0.mp4
    │   ├── 1.mp4
    │   └── ...
    └── ...

规则：
  - 如果 json 有 "prompt"：将其用作任务名称（清理为目录名）
  - 否则：回退到 LeRobot 元数据（需要 --lerobot_dir）
    - 如果未提供 lerobot_dir：打印警告并跳过该样本
"""

import argparse
import json
import shutil
from pathlib import Path
from collections import defaultdict
from typing import Dict, List, Optional, Tuple


def sanitize_task_name(task: str) -> str:
    """
    将任务描述转换为有效的目录名称。
    例如："Lift the red cube up." -> "Lift_the_red_cube_up"
    """
    task = task.strip()
    for ch in [".", ",", "!", "?", ":", ";", "\"", "'"]:
        task = task.replace(ch, "")
    task = task.replace(" ", "_")
    task = "_".join(filter(None, task.split("_")))
    return task


def load_tasks(tasks_file: Path) -> Dict[int, str]:
    """加载任务定义。返回 {task_index: task_string}"""
    tasks: Dict[int, str] = {}
    with open(tasks_file, "r") as f:
        for line in f:
            if not line.strip():
                continue
            data = json.loads(line)
            tasks[int(data["task_index"])] = data["task"]
    return tasks


def load_episodes(episodes_file: Path) -> List[dict]:
    """加载剧集信息。返回 dict 列表（episode_index、tasks、length 等）"""
    episodes: List[dict] = []
    with open(episodes_file, "r") as f:
        for line in f:
            if not line.strip():
                continue
            episodes.append(json.loads(line))
    return episodes


def build_episode_to_task_map(lerobot_dir: Path) -> Dict[int, str]:
    """
    构建映射：episode_index -> task_string（剧集中的第一个任务）
    """
    meta_dir = lerobot_dir / "meta"
    tasks_path = meta_dir / "tasks.jsonl"
    episodes_path = meta_dir / "episodes.jsonl"

    if not tasks_path.exists() or not episodes_path.exists():
        raise FileNotFoundError(f"LeRobot meta files not found under: {meta_dir}")

    _tasks = load_tasks(tasks_path)  # 不是严格必需的，但如果剧集以某种方式存储索引则有用
    episodes = load_episodes(episodes_path)

    ep2task: Dict[int, str] = {}
    for ep in episodes:
        ep_idx = int(ep["episode_index"])
        ep_tasks = ep.get("tasks", [])
        if not ep_tasks:
            continue

        # 在许多 LeRobot 数据集中，ep["tasks"] 已经存储任务字符串。
        # 如果它存储索引，您可以在此处扩展。我们将支持两者：
        t0 = ep_tasks[0]
        if isinstance(t0, int):
            task_str = _tasks.get(int(t0), str(t0))
        else:
            task_str = str(t0)

        ep2task[ep_idx] = task_str

    return ep2task


def read_json(path: Path) -> Optional[dict]:
    try:
        with open(path, "r") as f:
            return json.load(f)
    except Exception as e:
        print(f"[WARN] Failed to read json: {path} ({e})")
        return None


def parse_episode_index_from_stem(stem: str) -> Optional[int]:
    """
    尝试从文件名词干中提取剧集索引。
    它可以处理的示例：
      - episode_000123
      - ..._000123
      - 000123
    如果无法解析，返回 None。
    """
    # 最常见："episode_000123"
    if stem.startswith("episode_"):
        tail = stem[len("episode_") :]
        if tail.isdigit():
            return int(tail)

    # 尝试最后一个下划线块
    parts = stem.split("_")
    for candidate in reversed(parts):
        if candidate.isdigit():
            return int(candidate)

    # 整个词干是数字？
    if stem.isdigit():
        return int(stem)

    return None


def convert_cosmos_to_step2(
    cosmos_dir: Path,
    output_dir: Path,
    lerobot_dir: Optional[Path] = None,
    chunk_missing_prompt_policy: str = "skip",
):
    """
    将 cosmos2.5 输出转换为 step2 格式。

    chunk_missing_prompt_policy：
      - "skip"：如果没有提示且没有 lerobot_dir 映射，跳过该样本
    """
    cosmos_dir = cosmos_dir.resolve()
    output_dir = output_dir.resolve()
    output_dir.mkdir(parents=True, exist_ok=True)

    ep2task: Dict[int, str] = {}
    if lerobot_dir is not None:
        ep2task = build_episode_to_task_map(lerobot_dir.resolve())

    # 按词干收集对 (json, mp4)
    json_files = sorted(cosmos_dir.glob("*.json"))
    if not json_files:
        raise FileNotFoundError(f"No .json files found in cosmos_dir: {cosmos_dir}")

    # task_name -> 源 mp4 路径列表（有序）
    task_to_videos: Dict[str, List[Path]] = defaultdict(list)
    skipped: List[Tuple[Path, str]] = []

    for jpath in json_files:
        stem = jpath.stem
        mpath = cosmos_dir / f"{stem}.mp4"
        if not mpath.exists():
            print(f"[WARN] Missing mp4 for json: {jpath.name} -> expected {mpath.name}, skip.")
            skipped.append((jpath, "missing_mp4"))
            continue

        data = read_json(jpath)
        if data is None:
            skipped.append((jpath, "bad_json"))
            continue

        prompt = data.get("prompt", None)
        if isinstance(prompt, str) and prompt.strip():
            task_str = prompt.strip()
            task_dir_name = sanitize_task_name(task_str)
            task_to_videos[task_dir_name].append(mpath)
            continue

        # 没有提示 -> 回退到 lerobot 元数据映射
        if not ep2task:
            print(
                f"[WARN] {jpath.name} has no 'prompt'. "
                f"You didn't provide --lerobot_dir (or mapping is empty), cannot infer task. Skipping."
            )
            skipped.append((jpath, "no_prompt_no_lerobot"))
            continue

        ep_idx = parse_episode_index_from_stem(stem)
        if ep_idx is None:
            print(
                f"[WARN] {jpath.name} has no 'prompt' and episode index cannot be parsed from name '{stem}'. Skipping."
            )
            skipped.append((jpath, "no_prompt_cannot_parse_episode"))
            continue

        task_str = ep2task.get(ep_idx)
        if not task_str:
            print(
                f"[WARN] {jpath.name} has no 'prompt'. Parsed episode_index={ep_idx}, "
                f"but it's not found in lerobot meta. Skipping."
            )
            skipped.append((jpath, "episode_not_in_meta"))
            continue

        task_dir_name = sanitize_task_name(task_str)
        task_to_videos[task_dir_name].append(mpath)

    # 复制到输出文件夹，每个任务按顺序编号
    total_copied = 0
    for task_dir_name, vids in sorted(task_to_videos.items(), key=lambda x: x[0]):
        dst_task_dir = output_dir / task_dir_name
        dst_task_dir.mkdir(parents=True, exist_ok=True)

        # 保持确定性顺序
        vids_sorted = sorted(vids, key=lambda p: p.name)
        for i, src in enumerate(vids_sorted):
            dst = dst_task_dir / f"{i}.mp4"
            shutil.copy2(src, dst)
            total_copied += 1

        print(f"[OK] Task '{task_dir_name}': {len(vids_sorted)} videos")

    print("\nConversion complete!")
    print(f"  Total videos copied: {total_copied}")
    print(f"  Output directory: {output_dir}")

    if skipped:
        print(f"\n[SUMMARY] Skipped {len(skipped)} samples:")
        # 打印一些以提高可读性
        for p, reason in skipped[:20]:
            print(f"  - {p.name}: {reason}")
        if len(skipped) > 20:
            print(f"  ... and {len(skipped) - 20} more")


def main():
    parser = argparse.ArgumentParser(
        description="将 cosmos2.5 输出（+可选的 LeRobot 元数据）转换为 convert_directory 输出格式"
    )
    parser.add_argument("--cosmos_dir", type=str, required=True, help="包含 *.mp4 和 *.json 的 Cosmos 输出目录")
    parser.add_argument("--output_dir", type=str, required=True, help="输出目录")
    parser.add_argument(
        "--lerobot_dir",
        type=str,
        default=None,
        help="可选的 LeRobot 数据集目录（仅在 json 没有 'prompt' 时需要）",
    )

    args = parser.parse_args()

    cosmos_dir = Path(args.cosmos_dir)
    output_dir = Path(args.output_dir)
    lerobot_dir = Path(args.lerobot_dir) if args.lerobot_dir else None

    convert_cosmos_to_step2(
        cosmos_dir=cosmos_dir,
        output_dir=output_dir,
        lerobot_dir=lerobot_dir,
    )


if __name__ == "__main__":
    main()
```
</details>

**3.创建预处理脚本**
在 `GR00T-Dreams/IDM_dump/scripts/preprocess/` 下创建预处理助手脚本 `so101.sh`。
<details>
<summary><strong>GR00T-Dreams/IDM_dump/scripts/preprocess/so101.sh</strong></summary>

```sh
#!/bin/bash
set -e

# =============================================================================
# 配置
# =============================================================================

# 包含 Cosmos Predict 2.5 推理输出的目录。
# 此目录应包括由 Cosmos 模型生成的视频。
LEROBOT_INPUT="<path_to_cosmos-predict2.5/outputs/>"

# 工作目录，用于存储所有中间和最终 IDM 输出。
# 建议将其放在快速本地磁盘上。
WORK_DIR="<path_to_IDM_workdir>"

# 机器人体现类型（由 IDM 和 LeRobot 使用）。
ROBOT_TYPE="so101"

# 用于在 LeRobot 数据集结构中存储视频的键名。
# 这应与下游 IDM 脚本期望的观测键匹配。
VIDEO_KEY="observation.images.front"

# =============================================================================
# 中间目录（自动生成）
# =============================================================================

# 步骤 1 输出：从 Cosmos 输出转换的任务命名目录
STEP1_DIR="${WORK_DIR}/step1"

# 步骤 2 输出：分割的视频和文本指令
STEP2_DIR="${WORK_DIR}/step2"

# 步骤 3 输出：预处理视频（例如，调整大小、标准化）
STEP3_DIR="${WORK_DIR}/step3"

# 步骤 4 输出：最终 LeRobot 格式数据集
STEP4_DIR="${WORK_DIR}/${ROBOT_TYPE}.data"

# =============================================================================
# 步骤 1：将 Cosmos 输出转换为基于任务的目录结构
# =============================================================================
# - 读取 Cosmos Predict 输出
# - 按任务名称分组视频
# - 为下游预处理准备数据
python3 IDM_dump/scripts/preprocess_leisaac/cosmos2.5_to_step2_format.py \
    --cosmos_dir "${LEROBOT_INPUT}" \
    --output_dir "${STEP1_DIR}"

# =============================================================================
# 步骤 2：分割视频和指令
# =============================================================================
# - 将原始视频和文本指令分离到：
#     - videos/
#     - labels/
# - --recursive 标志允许处理嵌套的任务目录
python3 IDM_dump/scripts/preprocess_leisaac/split_video_instruction.py \
    --source_dir "${STEP1_DIR}" \
    --output_dir "${STEP2_DIR}" \
    --recursive

# =============================================================================
# 步骤 3：预处理视频
# =============================================================================
# - 将视频调整为 IDM 期望的分辨率
# - 必要时转换视频格式
# - 跨任务保留目录结构
python3 IDM_dump/scripts/preprocess_leisaac/preprocess_video.py \
    --src_dir "${STEP2_DIR}" \
    --dst_dir "${STEP3_DIR}" \
    --dataset "${ROBOT_TYPE}" \
    --original_width 640 \
    --original_height 480 \
    --recursive

# =============================================================================
# 重要使用说明
# =============================================================================
# 强烈建议：
#
#   1. 先运行步骤 1-3
#   2. 检查 ${STEP3_DIR} 的内容
#   3. 识别生成的任务目录名称
#   4. 手动将所需的任务目录名称复制到步骤 4
#
# 这样可以避免在知道任务名称之前硬编码它们，并
# 允许在不同任务中灵活重用此脚本。
#
# 示例：
#   ls ${STEP3_DIR}
#   → Lift_the_red_cube_up
#
# 然后使用：
#   --input_dir "${STEP3_DIR}/Lift_the_red_cube_up"
#
# =============================================================================

# =============================================================================
# 步骤 4：将预处理的数据转换为 LeRobot 数据集提醒
# =============================================================================
# --input_dir：
#   STEP3_DIR 下特定于任务的目录的路径。
#   目录名称必须与步骤 3 中生成的任务名称匹配。
#
# --output_dir：
#   LeRobot 格式数据集的目标目录。
#
# --fps：
#   输出数据集的目标帧率。
#
# --embodiment：
#   LeRobot/IDM 使用的机器人体现标识符。
#
# --video_key：
#   用于存储视频数据的观测键。
python3 IDM_dump/scripts/preprocess_leisaac/raw_to_lerobot.py \
    --input_dir "${STEP3_DIR}/Lift_the_red_cube_up" \
    --output_dir "${STEP4_DIR}" \
    --fps 16 \
    --embodiment "${ROBOT_TYPE}" \
    --video_key "${VIDEO_KEY}"

# =============================================================================
# 步骤 5：从 LeRobot 数据集转储 IDM 动作
# =============================================================================
# - 加载预训练的 IDM 检查点
# - 在 LeRobot 数据集上运行 IDM 推理
# - 导出预测的动作轨迹
#
# --checkpoint：
#   训练好的 IDM 检查点的路径。
#
# --dataset：
#   步骤 4 中生成的 LeRobot 数据集的路径。
#
# --output_dir：
#   存储 IDM 预测的输出目录。
#
# --num_gpus：
#   用于 IDM 推理的 GPU 数量。
#
# --video_indices：
#   要处理的视频索引（例如，“0 16”处理视频 0-16）。
python3 IDM_dump/scripts/preprocess_leisaac/dump_idm_actions.py \
    --checkpoint "<path_to_the_trained_IDM_checkpoint>" \
    --dataset "${STEP4_DIR}" \
    --output_dir "${STEP4_DIR}_idm_cosmos" \
    --num_gpus 1 \
    --video_indices "0 16"
```

</details>

**4.运行 IDM 推理**
运行推理脚本：
```bash
# 从 GR00T-Dreams 项目根目录运行此命令
# cd <path_to_GR00T-Dreams>
PYTHONPATH=. bash IDM_dump/scripts/preprocess/so101.sh
```
此步骤基于 Cosmos 生成的视频生成完整的 LeRobot 格式输出。


## 步骤 4：在 LeIsaac 中回放和评估

在此步骤中，**原始 HDF5 数据集** 和 **IDM 生成的 LeRobot 轨迹（parquet）** 首先被转换并合并为 **可回放的 LeIsaac HDF5 数据集**，然后使用 **LeIsaac** 在 **Isaac Sim** 中回放。此回放过程用于验证推断的动作轨迹的质量和物理合理性。

### 4.1 将 IDM 输出转换为 LeIsaac HDF5

IDM 推理以 **LeRobot parquet 格式** 生成动作轨迹。要在 LeIsaac 中处理这些轨迹，必须首先将它们转换为与 LeIsaac 兼容的 HDF5 格式。

切换到 **LeIsaac** 环境并从 **LeIsaac 项目目录** 运行转换脚本：

```bash
python scripts/convert/lerobot2isaaclab.py \
    --lerobot_dir <path_to_idm_output_lerobot> \
    --output_hdf5 <path_to_idm_output_hdf5> \
    --column_keys action observation.state
```

### 4.2 与源 HDF5 数据集合并

步骤 4.1 中生成的 HDF5 文件需要与源 LeIsaac HDF5 文件（来自第 1.1 章）合并，以恢复回放所需的初始状态。

```bash
python scripts/tutorials/cosmos_merge.py \
    --lerobot_hdf5 <path_to_idm_output_hdf5> \
    --source_hdf5 <path_to_source_leisaac_hdf5> \
    --output_hdf5 <path_to_output_hdf5>
```

### 4.3 在 LeIsaac 中回放生成的数据集

转换和合并后，最终的 **HDF5 数据集** 可以使用 **LeIsaac 的动作回放模式** 进行回放。您可以参考 **[dataset_replay](https://lightwheelai.github.io/leisaac/docs/getting_started/dataset_replay)** 获取详细说明。

<div align="center">
  <video src="https://github.com/user-attachments/assets/a4eff3dd-05c0-4213-b87c-faa01c384f86"
         controls
         width="100%">
  </video>
</div>
