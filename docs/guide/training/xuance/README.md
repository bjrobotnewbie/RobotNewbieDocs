# xuance

XuanCe 是一个统一的深度强化学习与多智能体强化学习算法库，支持多种后端和环境类型。

## 项目链接

- GitHub: <https://github.com/agi-brain/xuance>
- 项目主页: https://xuance.org

## 项目概述

XuanCe（玄策）提供高质量、模块化的 DRL/MARL 算法实现，目标是降低强化学习算法调参和复现实验的门槛。它支持 PyTorch、TensorFlow2、MindSpore 等深度学习后端，兼容 Gymnasium、PettingZoo 等环境接口，并提供并行环境、分布式训练、自动超参数搜索和 TensorBoard/WandB 可视化等能力。

项目覆盖丰富的单智能体和多智能体算法，适合做教学、算法复现、基准测试和应用研究。对于机器人和控制方向，XuanCe 可作为统一算法实验平台，将不同策略梯度、价值学习、actor-critic 和多智能体方法放在同一工程框架中比较，减少从零实现训练循环和日志系统的工作量。
