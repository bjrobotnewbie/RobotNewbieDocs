# MGDP

[Adv. Sci. 2026] MGDP: 面向四足 locomotion 的通用深度感知模型掌握

## 项目链接

- GitHub: <https://github.com/arclab-hku/MGDP>
- 项目主页: https://arclab-hku.github.io/MGDP/

## 项目概述

## 项目介绍
本项目名为MGDP，全称Mastering a Generalized Depth Perception Model for Quadruped Locomotion，针对现有基于感知的深度强化学习（DRL）四足机器人控制器存在的地形通用性差、平台迁移能力弱、计算开销高、对传感器噪声敏感等问题，提出了通用控制框架。
项目基于NVIDIA Warp实现深度图像高效并行计算，从深度图、高度图多模态输入中提取低维地形特征，集成显式深度图去噪机制，实现感知与动力学解耦并降低内存占用；同时设计地形自适应奖励函数，无需蒸馏即可在单次训练中让模型掌握攀爬、跳跃、爬行、挤过狭窄空间等复杂运动技能。

## 主要特性
1.  支持跨地形泛化，拥有优异的复杂地形运动能力
2.  预训练感知模型可快速适配不同形态的四足机器人，实现高效微调
3.  采用NVIDIA Warp降低计算开销，集成去噪机制提升鲁棒性
4.  实现感知与动力学解耦，简化训练流程并降低资源占用
5.  适配ROS、SLAM相关机器人感知落地场景，可用于四足机器人通用运动控制研发
