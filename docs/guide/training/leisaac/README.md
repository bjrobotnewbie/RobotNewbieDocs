# LeIsaac

- [**原英文文档**](https://lightwheelai.github.io/leisaac/)

LeIsaac 在 [IsaacLab](https://isaac-sim.github.io/IsaacLab/main/index.html) 中使用 SO101Leader（[LeRobot](https://github.com/huggingface/lerobot)）提供遥操作功能，包括数据收集、数据转换和后续的策略训练。

- 🤖 我们在 IsaacLab 中使用 SO101 Follower 机器人（和其他相关机器人），并提供实用的遥操作方法。
- 🦾 状态机脚本策略实现完全自动化的数据收集，无需人工遥操作。
- 🔄 开箱即用的脚本将 HDF5 数据转换为 LeRobot 数据集格式。
- 🧠 仿真数据用于微调 [GR00T N1.5](https://github.com/NVIDIA/Isaac-GR00T) 并在真实硬件上部署策略。未来将支持更多策略。

## 文档导航

- [介绍](./introduction.md)
- [快速开始](./getting_started/README.md)
- [教程](./tutorials/README.md)
- [额外功能](./features/README.md)
- [故障排除](./trouble_shooting.md)
- [云仿真](./cloud_simulation/README.md)
