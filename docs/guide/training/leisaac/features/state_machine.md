# 状态机数据生成

状态机模块为操作任务提供自动化数据收集，无需人工遥操作。它运行脚本化策略并将演示记录到 HDF5 数据集中。

## 录制

```shell
python scripts/datagen/state_machine/generate.py \
    --task LeIsaac-SO101-PickOrange-v0 \
    --num_envs 1 \
    --device cuda \
    --enable_cameras \
    --record \
    --dataset_file ./datasets/pick_orange.hdf5 \
    --num_demos 50
```

<details>
<summary><strong>generate.py 参数说明</strong></summary>

- `--task`：要运行的任务环境名称，例如 `LeIsaac-SO101-PickOrange-v0`。可用任务请参考[此处](../resources/available_env.md)。

- `--num_envs`：并行仿真环境数量，通常为 `1`。

- `--device`：计算设备，如 `cpu` 或 `cuda`（GPU）。

- `--enable_cameras`：启用相机传感器以收集视觉数据。

- `--seed`：环境的随机种子。如果未设置，默认为当前时间戳。

- `--record`：启用数据录制；将演示保存到 HDF5 文件。

- `--dataset_file`：保存录制数据集的路径，例如 `./datasets/pick_orange.hdf5`。

- `--resume`：从现有数据集文件恢复录制。

- `--num_demos`：要录制的成功演示数量。设置为 `0` 表示无限。

- `--step_hz`：环境步进频率，单位为 Hz（默认：`60`）。

- `--quality`：启用高质量渲染模式。

- `--use_lerobot_recorder`：直接以 LeRobot Dataset 格式录制，而不是 HDF5。

- `--lerobot_dataset_repo_id`：HuggingFace 数据集仓库 ID（格式：`username/repository_name`）。设置 `--use_lerobot_recorder` 时需要。

- `--lerobot_dataset_fps`：使用 LeRobot 录制器时的数据集帧率（默认：`30`）。

</details>

::::tip
抓取成功率在很大程度上取决于橙子的生成位置。调整任务环境配置文件中的生成位置（例如将橙子移近机器人基座）可以显著提高成功率。
::::

## 回放

录制完成后，您可以在仿真中回放收集的演示：

```shell
python scripts/datagen/state_machine/replay.py \
    --task LeIsaac-SO101-PickOrange-v0 \
    --dataset_file ./datasets/pick_orange.hdf5 \
    --task_type so101_state_machine \
    --select_episodes 0 \
    --device cuda \
    --enable_cameras \
    --replay_mode action
```

<details>
<summary><strong>replay.py 参数说明</strong></summary>

- `--task`：要运行的任务环境名称，例如 `LeIsaac-SO101-PickOrange-v0`。

- `--num_envs`：并行仿真环境数量，通常为 `1`。

- `--device`：计算设备，如 `cpu` 或 `cuda`（GPU）。

- `--enable_cameras`：启用相机传感器以在回放过程中可视化。

- `--dataset_file`：录制数据集的路径，例如 `./datasets/pick_orange.hdf5`。

- `--replay_mode`：回放模式 — `action` 回放 IK 位姿目标，`state` 回放关节位置。

- `--task_type`：录制时使用的状态机设备类型，例如 `so101_state_machine` 或 `bi_so101_state_machine`。如果未设置，则从任务名称推断。

- `--select_episodes`：要回放的回合索引列表。留空则回放所有回合。

- `--step_hz`：环境步进频率，单位为 Hz（默认：`60`）。

</details>

## 添加新任务

1. 在 `source/leisaac/leisaac/datagen/state_machine/` 中实现 `StateMachineBase` 子类。
2. 在 `scripts/datagen/state_machine/generate.py` 的 `TASK_REGISTRY` 中注册：

```python
TASK_REGISTRY = {
    "LeIsaac-SO101-PickOrange-v0": (PickOrangeStateMachine, "so101_state_machine"),
    "LeIsaac-MY-NewTask-v0":       (MyNewStateMachine,      "so101_state_machine"),
}
```
