# 策略训练与推理

## 1. 数据约定

收集的遥操作数据以 HDF5 格式存储在指定目录中。我们提供了一个脚本将 HDF5 数据转换为 LeRobot Dataset 格式。只有成功的回合才会被转换。

在运行转换脚本之前，您必须先安装 LeRobot 相关依赖项：

```bash
pip install lerobot==0.3.3
pip install numpy==1.26.0
```

然后您可以运行以下命令执行数据转换。此脚本将 HDF5 数据集转换为 LeRobot Dataset v2 格式。

```bash
python scripts/convert/isaaclab2lerobot.py \
    --task_name=LeIsaac-SO101-PickOrange-v0 \
    --repo_id=EverNorif/so101_test_orange_pick \
    --hdf5_root=./datasets \
    --hdf5_files=dataset.hdf5
```

<details>
<summary><strong>isaaclab2lerobot.py 参数说明</strong></summary><p></p>

- `--task_name`：任务名称，例如 `LeIsaac-SO101-PickOrange-v0`。

- `--task_type`：指定任务类型。如果您的数据集是使用键盘/游戏手柄录制的，应将其设置为 'keyboard'/'gamepad'，否则不设置并保持默认值 None。

- `--repo_id`：指定 LeRobot Dataset 仓库 ID，例如 `EverNorif/so101_test_orange_pick`

- `--fps`：指定 LeRobot Dataset 的帧率。

- `--hdf5_root`：HDF5 根目录。

- `--hdf5_files`：HDF5 文件（逗号分隔）。如果未提供，则使用 hdf5_root 中的 dataset.hdf5

- `--task_description`：任务描述。如果未提供，将使用任务中定义的描述。

- `--push_to_hub`：是否将数据集推送到 huggingface hub。

</details>

:::tip
我们还提供 `isaaclab2lerobotv3.py` 脚本，将 HDF5 数据集转换为 LeRobot Dataset v3 格式。它需要以下版本的 LeRobot 相关依赖项：

```bash
pip install lerobot==0.4.2
pip install numpy==1.26.0
```

`isaaclab2lerobotv3.py` 的可用参数与 `isaaclab2lerobot.py` 相同。
:::

## 2. 策略训练

以 [GR00T N1.5](https://github.com/NVIDIA/Isaac-GR00T) 为例，它提供了基于 LeRobot Dataset 的微调工作流。您可以参考 [nvidia/gr00t-n1.5-so101-tuning](https://huggingface.co/blog/nvidia/gr00t-n1-5-so101-tuning) 使用您收集的 lerobot 数据对其进行微调。我们以 pick-orange 任务为例。

完成策略训练后，您将获得一个检查点，可用于使用 GR00T N1.5 提供的 `inference_service.py` 启动推理服务。

## 3. 策略推理

我们还提供了在仿真中运行策略推理的接口。首先，您需要安装额外的依赖项：

```bash
pip install -e "source/leisaac[gr00t]"
```

然后，您需要启动 GR00T N1.5 推理服务器。您可以参考 [GR00T 评估文档](https://github.com/NVIDIA/Isaac-GR00T/tree/4af2b622892f7dcb5aae5a3fb70bcb02dc217b96?tab=readme-ov-file#4-evaluation) 获取详细说明。

:::tip
最新的 GR00T 仓库现在指向 N1.6。请参考上述相应提交以获取有关 N1.5 的信息。您还可以在 [可用策略推理](../resources/available_policy.md) 中找到更详细的提交信息。
:::

之后，您可以使用以下脚本开始推理：

```shell
python scripts/evaluation/policy_inference.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --eval_rounds=10 \
    --policy_type=gr00tn1.5 \
    --policy_host=localhost \
    --policy_port=5555 \
    --policy_timeout_ms=5000 \
    --policy_action_horizon=16 \
    --policy_language_instruction="Pick up the orange and place it on the plate" \
    --device=cuda \
    --enable_cameras
```

<details>
<summary><strong>policy_inference.py 参数说明</strong></summary><p></p>

- `--task`：要运行推理的任务环境名称（例如 `LeIsaac-SO101-PickOrange-v0`）。

- `--seed`：环境的随机种子（默认：当前时间）。

- `--episode_length_s`：回合长度，单位为秒（默认：`60`）。

- `--eval_rounts`：评估轮数。0 表示不添加超时终止，策略将运行直到成功或手动重置（默认：`0`）

- `--policy_type`：要使用的策略类型（默认：`gr00tn1.5`）。
    - 现在我们支持 `gr00tn1.5`、`gr00tn1.6`、`lerobot-<model_type>`

- `--policy_host`：策略服务器的主机地址（默认：`localhost`）。

- `--policy_port`：策略服务器的端口（默认：`5555`）。

- `--policy_timeout_ms`：策略服务器的超时时间，单位为毫秒（默认：`5000`）。

- `--policy_action_horizon`：每次推理预测的动作数量（默认：`16`）。

- `--policy_language_instruction`：策略的语言指令（例如，自然语言中的任务描述）。

- `--policy_checkpoint_path`：策略检查点的路径（如果需要）。

- `--device`：计算设备，如 `cpu` 或 `cuda`。

您还可以使用 IsaacLab 的 `AppLauncher` 支持的其他参数（详见其文档）。

</details>

## 4. 示例

我们提供了仿真收集的数据（Pick Orange）和相应的微调后的 GR00T N1.5 策略，可以从以下链接下载：

- `dataset`: https://huggingface.co/datasets/LightwheelAI/leisaac-pick-orange
- `policy`: https://huggingface.co/LightwheelAI/leisaac-pick-orange-v0

以下视频演示了仿真中的推理结果，对应两个不同的任务。两个任务都遵循完整的工作流程：仿真中的数据收集、微调 GR00T N1.5 以及仿真中的推理。

| PickOrange | LiftCube |
| ---------- | -------- |
| <video src="https://github.com/user-attachments/assets/26c2b91d-3886-4fc5-839c-140d3839036b" autoPlay loop muted playsInline style="max-height: 250px;"></video> | <video src="https://github.com/user-attachments/assets/03f0649d-ddb6-419d-b4d9-e45cb91b2aa9" autoPlay loop muted playsInline style="max-height: 250px;"></video> |
