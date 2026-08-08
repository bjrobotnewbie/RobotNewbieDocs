# crazyflow

Crazyflow 是基于 JAX 的四旋翼无人机研究仿真器，支持批量、可微和 GPU 加速仿真。

## 项目链接

- GitHub: <https://github.com/learnsyslab/crazyflow>

## 项目概述

Crazyflow 面向 Crazyflie 2.x 等四旋翼无人机的高速仿真实验，使用 JAX 在 CPU/GPU 上运行批量可微仿真。它可以同时模拟大量独立环境和多无人机场景，并支持通过 `jax.grad` 对动力学和控制管线求导，适合控制优化、系统辨识、强化学习和大规模参数扫描。

项目强调研究效率和并行能力，提供解析模型、抽象模型、状态控制接口和文档示例。对于需要在大量并行 world 中训练或评估无人机控制策略的研究者，Crazyflow 提供了比传统逐实例仿真更适合现代加速硬件的基础设施。
