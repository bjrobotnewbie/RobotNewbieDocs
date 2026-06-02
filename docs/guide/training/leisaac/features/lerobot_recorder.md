# LeRobot 录制器
> LeRobot 数据集录制器：在遥操作过程中直接记录 LeRobot 格式的数据集

LeRobot 录制器是 LeIsaac 提供的增强功能，允许用户在遥操作过程中直接以 LeRobot 格式记录数据。此功能无缝集成到遥操作工作流程中，生成 LeRobot 标准数据集，无需额外的数据转换步骤。

## 工作原理

LeRobot 录制器将默认的录制管理器替换为 `LeRobotRecorderManager`。在每次环境步进后：

1. **数据收集**：收集当前步的观测值（包括关节位置、相机图像等）和动作
2. **格式转换**：通过 `build_lerobot_frame` 方法将数据转换为 LeRobot 帧格式
3. **缓冲区管理**：将帧数据添加到 LeRobot Dataset 缓冲区
4. **回合处理**：当回合结束时，根据任务成功状态决定是否保存：
   - **成功**：调用 `flush()` 将整个回合保存到数据集
   - **失败**：调用 `clear()` 清除缓冲区而不保存数据

LeIsaac 会自动跳过每个回合的前 5 帧，以避免初始状态的不稳定性影响数据质量。

## 使用方法

LeRobot 录制器需要 lerobot 依赖。安装说明请参考[此部分](../getting_started/installation#optional-install-lerobot)。

要在遥操作过程中以 LeRobot 格式记录数据，请使用以下命令：

```shell
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=so101leader \
    --port=/dev/ttyACM0 \
    --num_envs=1 \
    --device=cuda \
    --enable_cameras \
    --record \
    --use_lerobot_recorder \
    --lerobot_dataset_repo_id=EverNorif/test_lerobot_recorder \
    --lerobot_dataset_fps=30
```

只需启用 `--use_lerobot_recorder` 并指定 `repo_id` 和 `dataset_fps`，即可在遥操作过程中直接以 LeRobot Dataset 格式记录数据。

## 参数说明

- `--use_lerobot_recorder`：启用 LeRobot 格式录制器
- `--lerobot_dataset_repo_id`：HuggingFace 数据集仓库 ID（格式：`username/repository_name`）
- `--lerobot_dataset_fps`：数据集帧率，通常设置为 30 FPS

::::tip
与录制为 hdf5 相比，LeRobot 录制器集成可能会导致遥操作出现轻微延迟。如果遇到此问题，可以考虑不使用 `--use_lerobot_recorder`。
::::
