# LeIsaac
- 中文文档: https://zihao-ai.feishu.cn/wiki/space/7589642043471924447

- [**原英文文档**](https://lightwheelai.github.io/leisaac/)

LeIsaac 在 [IsaacLab](https://isaac-sim.github.io/IsaacLab/main/index.html) 中使用 SO101Leader（[LeRobot](https://github.com/huggingface/lerobot)）提供遥操作功能，包括数据收集、数据转换和后续的策略训练。

- 🤖 我们在 IsaacLab 中使用 SO101 Follower 机器人（和其他相关机器人），并提供实用的遥操作方法。
- 🦾 状态机脚本策略实现完全自动化的数据收集，无需人工遥操作。
- 🔄 开箱即用的脚本将 HDF5 数据转换为 LeRobot 数据集格式。
- 🧠 仿真数据用于微调 [GR00T N1.5](https://github.com/NVIDIA/Isaac-GR00T) 并在真实硬件上部署策略。未来将支持更多策略。

## 文档导航

- [介绍](./introduction.md)
- [快速开始](./getting_started/README)
- [教程](./tutorials/README)
- [额外功能](./features/README)
- [故障排除](./trouble_shooting.md)
- [云仿真](./cloud_simulation/README)

- [lerobot-sim2real（LeRobot sim2real 代码。…）](/guide/training/leisaac/lerobot-sim2real/README)

- [cyclo_lab（此仓库提供了使用ROBOTIS机器人进行…）](/guide/training/leisaac/cyclo_lab/README)

- [basic-locomotion-isaaclab（适用于基本四足机器人任务的 IsaacL…）](/guide/training/leisaac/basic-locomotion-isaaclab/README)

- [WBC-AGILE（人类 humanoid 局部 - 操作学…）](/guide/training/leisaac/WBC-AGILE/README)

- [physical-ai-studio（物理 AI 工作室是一个端到端的框架，用…）](/guide/training/leisaac/physical-ai-studio/README)

- [cyclotron（基于 Isaac Lab 构建的官方强化…）](/guide/training/leisaac/cyclotron/README)

- [phosphobot（控制人工智能机器人。社区驱动的 UI 中…）](/guide/training/leisaac/phosphobot/README)

- [robot_lab（基于 IsaacLab 的机器人 RL …）](/guide/training/leisaac/robot_lab/README)
