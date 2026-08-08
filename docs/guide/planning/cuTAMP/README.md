# cuTAMP

cuTAMP 是 NVIDIA Research 开源的可微分 GPU 并行任务与运动规划框架，用于加速机器人 TAMP 搜索与优化。

## 项目链接

- GitHub: <https://github.com/NVlabs/cuTAMP>
- 项目主页: https://cutamp.github.io

## 项目概述

cuTAMP 是一个面向任务与运动规划（Task and Motion Planning, TAMP）的研究型框架，核心目标是利用 GPU 并行能力和可微分优化思想，加速复杂机器人任务中的动作选择、连续参数搜索和运动可行性评估。项目对应 RSS 2025 论文 “Differentiable GPU-Parallelized Task and Motion Planning”。

传统 TAMP 需要同时处理离散任务序列和连续运动约束，搜索空间往往非常大。cuTAMP 依赖 cuRobo 等 GPU 机器人运动规划能力，将多个候选计划、参数和约束评估并行化，并支持在软代价、计划骨架搜索、装箱/摆放等示例中进行优化。README 中也强调它需要较新的 NVIDIA GPU、Python 和 PyTorch 环境。

该项目适合机器人任务规划、机械臂操作、GPU 加速规划、可微分机器人优化和 TAMP 论文复现。它更偏研究前沿与高性能实验平台，适合有 CUDA/GPU 环境并希望探索复杂操作任务规划加速方法的用户。