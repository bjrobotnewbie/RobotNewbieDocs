# warp

NVIDIA Warp 是 Python 框架，可将普通 Python 函数 JIT 编译为 CPU/GPU 高效 kernel，用于仿真、机器人和机器学习。

## 项目链接

- GitHub: <https://github.com/NVIDIA/warp>
- 项目主页: https://nvidia.github.io/warp/stable/

## 项目概述

Warp 提供面向物理仿真、机器人、几何处理和机器学习的 GPU 加速计算能力。用户可以用 Python 编写 kernel，Warp 会 JIT 编译为可在 CPU 或 GPU 上运行的高效代码；其 kernel 支持可微分计算，并可嵌入 PyTorch、JAX、Paddle 等机器学习管线。

项目包含粒子、网格、有限元、布料、软体/刚体、机器人和碰撞等相关原语，适合构建自定义高性能仿真和优化任务。对于机器人学习与物理 AI 研究，Warp 可作为底层 differentiable simulation 与并行几何计算工具，帮助把物理模型和学习算法放入统一可微管线。
