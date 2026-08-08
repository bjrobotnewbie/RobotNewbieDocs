# basic-locomotion-isaaclab

适用于基本四足机器人任务的 IsaacLab DirectEnv，支持多四足机器人、模拟到模拟（sim-to-sim）以及模拟到真实（sim-to-real）的管道。

## 项目链接

- GitHub: <https://github.com/iit-DLSLab/basic-locomotion-isaaclab>

## 项目概述

## 项目介绍
本项目是基于IsaacLab的四足机器人基础运动强化学习DirectEnv实现，支持多款四足机器人，提供sim-to-sim与sim-to-real迁移流程。可用于四足机器人运动控制的RL训练、仿真间迁移以及真实机器人部署。支持通过ROS2完成真实机器人部署，搭配官方配套工具实现状态估计与机器人通信。

## 主要特性
1.  内置多项前沿技术：并发状态估计器、快速电机适配、形态对称性优化、对抗运动先验
2.  支持通过pace工具完成机器人参数辨识，实现sim2real适配
3.  支持Mujoco的sim-to-sim迁移，以及基于ROS2的sim-to-real部署
4.  适配Aliengo、Go2、B2、HyQReal2等多款四足机器人，提供平地、粗糙地形、视觉感知三类运动环境
5.  正在开发中特性：深度图到动作的策略蒸馏、深度图转高度图、激光点云转高度图网络
