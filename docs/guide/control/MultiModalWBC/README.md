# MultiModalWBC (M3imic)

- 项目链接：https://github.com/Renforce-Dynamics/MultiModalWBC

## 项目概述

MultiModalWBC (M3imic) 是一个完全开源、基于 IsaacLab 的框架，专为腿足机器人的多模态全身控制设计，支持运动模仿、运动跟踪及任务条件控制。该框架将机器人的本体感知状态与多模态人类运动条件统一到一个一致的接口中。

这是一个面向研究的框架，用于从异构运动信号中学习人形和通用关节机器人的全身控制策略。构建在 NVIDIA Isaac Sim / Isaac Lab 和 RSL-RL 之上，该框架面向大规模并行仿真和多模态模仿学习，专注于鲁棒运动跟踪和跨模态具身化。

核心理念是将全身控制视为多模态序列对齐问题：机器人策略通过联合以机器人为中心的状态和外部运动描述符（如人体姿态 SMPL-X 和 SE(3) 关键点）来协调全身动力学。

主要特点：
- 目前主要关注 Unitree G1 人形机器人，但设计可扩展到其他人形或全身平台
- 已被 IEEE Robotics and Automation Letters (RA-L) 接收
- 基于 BSD-3-Clause 开源
- 支持大规模并行仿真和多模态模仿学习

项目针对多模态运动模仿学习提供了完整的开源框架。
