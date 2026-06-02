# 数据集回放

遥操作完成后，您可以使用以下脚本在仿真环境中回放收集的数据集：

```shell
python scripts/environments/teleoperation/replay.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --num_envs=1 \
    --device=cuda \
    --enable_cameras \
    --replay_mode=action \
    --dataset_file=./datasets/dataset.hdf5 \
    --select_episodes 1 2
```

<details>
<summary><strong>replay.py 参数说明</strong></summary><p></p>

- `--task`：指定要运行的任务环境名称，例如 `LeIsaac-SO101-PickOrange-v0`。

- `--num_envs`：设置并行仿真环境的数量，回放时通常为 `1`。

- `--device`：指定计算设备，如 `cpu` 或 `cuda`（GPU）。

- `--enable_cameras`：启用相机传感器以在回放时可视化。

- `--replay_mode`：回放模式，我们支持回放 `action`（动作）或 `state`（状态）。

- `--task_type`：指定任务类型。如果您的数据集是使用键盘录制的，应将其设置为 `keyboard`，否则不设置并保持默认值 None。

- `--dataset_file`：录制数据集的路径，例如 `./datasets/record_data.hdf5`。

- `--select_episodes`：要回放的回合索引列表，留空则回放所有回合。

</details>

:::tip
如果您使用 Leader 以外的设备（例如键盘或游戏手柄）录制数据集，请将 `task_type` 设置为相应的设备，例如 `--task_type=keyboard` 或 `--task_type=gamepad`。

对于 Lekiwi 相关任务，默认的 `task_type` 是 `lekiwi-leader`。如果您使用其他设备收集数据，同样应将 `task_type` 设置为相应的设备。
:::
