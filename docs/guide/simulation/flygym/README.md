# flygym

- 项目链接：https://github.com/NeLy-EPFL/flygym
- 项目主页：https://neuromechfly.org/

## 项目概述

FlyGym 是 **NeuroMechFly v2** 的 Python 库，提供了成年果蝇（*Drosophila melanogaster*）的高保真数字孪生仿真环境，用于研究具身感觉运动控制。

FlyGym 2.x 版本在 2026 年进行了完全重写，性能大幅提升。

### 性能提升（v2.x）

- **CPU 仿真约 10 倍加速**：达到约 2 倍实时吞吐量
- **GPU 仿真约 300 倍加速**：通过 Warp/MJWarp 实现约 60 倍实时吞吐量
- **改进的场景合成工作流**
- **交互式查看器**
- **简化的依赖栈**

### 核心特点

- **高保真生物力学**：详细的果蝇肌肉骨骼模型，包含关节、肌肉、附肢
- **多模态感知**：仿真视觉、嗅觉感知
- **复杂地形行走**：支持在挑战性地形上行走仿真
- **环境交互**：果蝇可以与环境进行物理交互
- **GPU 加速**：支持大规模并行仿真，便于强化学习研究

### 适用研究领域

- 计算神经科学
- 果蝇运动控制研究
- 生物启发机器人学
- 具身智能研究
- 强化学习在生物系统中的应用

FlyGym 由 EPFL NeLy 实验室开发，是研究果蝇运动神经控制的开放仿真平台，最新版本性能大幅提升，支持更快的大规模研究。

> 旧版本 FlyGym 1.x.x 已迁移到 [flygym-gymnasium](https://github.com/NeLy-EPFL/flygym-gymnasium)。
