# mppi_playground

- 项目链接：https://github.com/kohonda/mppi_playground

## 项目概述
mppi_playground是一个基于PyTorch的模型预测路径积分控制（MPPI）实现库，核心特点包括：
1. 采用GPU加速的并行计算，提升计算效率
2. 基于PyTorch的可微实现，方便与深度学习框架集成
3. 灵活的动力学和成本函数定义，支持多种应用场景
4. 提供自动温度调整和Savitzky–Golay轨迹平滑等额外功能
5. 包含多个示例应用，如2D导航、赛车、摆锤、Cartpole和山地车等

该库支持Ubuntu 20.04及以上系统，可通过uv进行依赖管理，适合用于机器人控制、自动驾驶等领域的MPPI算法研究和开发。