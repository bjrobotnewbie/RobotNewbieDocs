---
sidebar_position: 1
slug: /
---

# LeIsaac

<div style="width: 100%; max-width: 960px; margin: 0 auto;">
  <video controls preload="metadata" style="width: 100%; border-radius: 8px;">
    <source src="https://github.com/user-attachments/assets/763acf27-d9a9-4163-8651-3ba0a6a185d7" />
  </video>
</div>

LeIsaac 在 [IsaacLab](https://isaac-sim.github.io/IsaacLab/main/index.html) 中使用 SO101Leader（[LeRobot](https://github.com/huggingface/lerobot)）提供遥操作功能，包括数据收集、数据转换和后续的策略训练。

- 🤖 我们在 IsaacLab 中使用 SO101 Follower 机器人（和其他相关机器人），并提供实用的遥操作方法。
- 🦾 状态机脚本策略实现完全自动化的数据收集，无需人工遥操作。
- 🔄 开箱即用的脚本将 HDF5 数据转换为 LeRobot 数据集格式。
- 🧠 仿真数据用于微调 [GR00T N1.5](https://github.com/NVIDIA/Isaac-GR00T) 并在真实硬件上部署策略。未来将支持更多策略。
