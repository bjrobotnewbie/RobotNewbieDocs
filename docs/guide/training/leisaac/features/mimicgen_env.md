# MimicGen 环境
> MimicGen 环境：从演示中生成数据

我们集成了 [IsaacLab MimicGen](https://isaac-sim.github.io/IsaacLab/main/source/overview/imitation-learning/teleop_imitation.html)，这是一个强大的功能，可以从专家演示中自动生成额外的演示。

要使用此功能，您首先需要记录一些演示。录制脚本可以参考上面的说明。（下面我们以 `LeIsaac-SO101-LiftCube-v0` 任务的 MimicGen 为例）。

:::info
请注意以下脚本中的 `input_file` 和 `output_file` 参数。通常，前一个脚本的 `output_file` 会成为下一个脚本的 `input_file`。
:::

由于 MimicGen 需要基于末端执行器位姿和对象位姿进行轨迹泛化，我们首先将基于关节位置的动作数据转换为基于 IK（逆运动学）的动作数据。转换过程如下，其中 `input_file` 指定收集的演示数据：

```shell
python scripts/mimic/eef_action_process.py \
    --input_file ./datasets/mimic-lift-cube-example.hdf5 \
    --output_file ./datasets/processed_mimic-lift-cube-example.hdf5 \
    --to_ik --headless
```

接下来，我们基于转换后的动作数据进行子任务标注。标注可以通过两种方式进行：自动和手动。如果您想使用自动标注，请添加 `--auto` 启动选项。

```shell
python scripts/mimic/annotate_demos.py \
    --device cuda \
    --task LeIsaac-SO101-LiftCube-Mimic-v0 \
    --input_file ./datasets/processed_mimic-lift-cube-example.hdf5 \
    --output_file ./datasets/annotated_mimic-lift-cube-example.hdf5 \
    --enable_cameras
```

标注完成后，我们可以进行数据生成。生成过程如下：

```shell
python scripts/mimic/generate_dataset.py \
    --device cuda \
    --num_envs 1 \
    --generation_num_trials 10 \
    --input_file ./datasets/annotated_mimic-lift-cube-example.hdf5 \
    --output_file ./datasets/generated_mimic-lift-cube-example.hdf5 \
    --enable_cameras
```

获得生成的数据后，我们还提供了一个转换脚本，将其从基于 IK 的动作数据转换回基于关节位置的动作数据，如下所示：

```shell
python scripts/mimic/eef_action_process.py \
    --input_file ./datasets/generated_mimic-lift-cube-example.hdf5 \
    --output_file ./datasets/final_generated_mimic-lift-cube-example.hdf5 \
    --to_joint --headless
```

最后，您可以使用回放功能查看生成数据的效果。值得注意的是，由于 IsaacLab 仿真固有的随机性，回放性能可能会有所不同。

:::info
根据用于收集数据的设备，您需要使用 `--task_type` 指定相应的任务类型。例如，如果您的演示是使用键盘收集的，则在运行 `annotate_demos` 和 `generate_dataset` 时添加 `--task_type=keyboard`。

回放 `final_generated_dataset.hdf5` 的结果时不需要提供 `task_type`。
:::

作为参考，我们还提供了示例数据，包括[原始收集的数据](https://huggingface.co/spaces/lerobot/visualize_dataset?path=%2FLightwheelAI%2Fleisaac-pick-orange%2Fepisode_0)和 [MimicGen 生成的数据](https://huggingface.co/spaces/lerobot/visualize_dataset?path=%2FLightwheelAI%2Fleisaac-pick-orange-mimic-v0%2Fepisode_0)。
