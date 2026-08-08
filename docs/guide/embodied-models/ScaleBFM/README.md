# ScaleBFM

《Scaling Behavior Foundation Model for Humanoid Robots》论文的官方实现

## 项目链接

- GitHub: <https://github.com/zengweishuai/ScaleBFM>

## 项目概述

## 项目介绍
ScaleBFM是论文《Scaling Behavior Foundation Model for Humanoid Robots》的官方实现，旨在通过学习范式、行为数据和模型架构的协同设计，实现行为基础模型的规模化扩展。该框架可让类人机器人在仿真与真实环境中完成敏捷行走、灵巧操作、协同控操等多种具备自然全身协调能力的行为。
项目包含两个核心工具链：ScaleRetarget用于将通用动捕数据转换为适配Unitree G1类人机器人的关节轨迹；ScaleTrack提供BFM预训练流水线，可将重定向后的轨迹打包为数据集，并基于IsaacLab结合RSL-RL完成模型预训练，支持单/多GPU训练、策略回放与导出。

## 主要特性
1.  支持类人机器人全场景行为规模化训练，覆盖敏捷运动、灵巧操作与协同控操
2.  配套Motion Retargeting工具，可将多源动捕数据转换为适配Unitree G1的机器人轨迹
3.  完整的预训练流水线，支持仿真环境下的多GPU并行训练与模型导出
4.  可在仿真与真实机器人场景中部署落地
