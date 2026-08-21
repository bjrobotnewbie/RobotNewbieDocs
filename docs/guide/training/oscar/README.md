# oscar

基于数据的操作空间自适应与鲁棒机器人操纵

## 项目链接

- GitHub: <https://github.com/NVlabs/oscar>
- 项目主页: <https://cremebrule.github.io/oscar-web>

## 项目概述

## 项目介绍
该项目是NVIDIA发布的OSCAR，即数据驱动的操作空间控制框架，用于自适应且鲁棒的机器人操作。它基于IsaacGym构建，是模块化的大规模机器人训练研究框架，现已停止维护不再更新。项目提供了配套的论文、项目主页，可用于机器人操纵算法的 benchmark 与快速原型开发。

## 主要特性
1.  基于PyTorch实现并并行化了OSC、逆运动学、关节控制三种高质量控制器
2.  内置多款复杂机器人操纵任务用于学习算法基准测试
3.  模块化架构支持快速新增机器人、控制器与训练环境
4.  支持训练、零样本评估、微调等完整机器人学习工作流

该项目依赖Linux系统、Conda、NVIDIA GPU与CUDA环境，需配合IsaacGym Preview 3.0及以上版本使用。
