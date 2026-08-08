# NeuPAN

[TRO 2025] NeuPAN: 基于端到端模型学习的直接点式机器人导航

## 项目链接

- GitHub: <https://github.com/hanruihua/NeuPAN>
- 项目主页: https://hanruihua.github.io/neupan_project/

## 项目概述

## 项目介绍
NeuPAN（Neural Proximal Alternating-minimization Network）是一款发表于TRO 2025的端到端基于模型学习的机器人运动规划器，支持直接从障碍物点云数据输出控制指令。它融合了学习与优化技术，无需构建环境地图，可在杂乱未知环境中高效安全地完成机器人导航，同时避免了传统导航流水线的中间模块误差传递问题，具备实时性强、部署简单的特点。项目还提供了ROS/ROS2封装包，支持真实机器人部署。

## 主要特性
1.  **端到端模型学习**：直接将点云障碍物数据映射为机器人控制动作，无需中间感知与规划模块
2.  **实时无地图导航**：可在未知杂乱环境中快速完成导航任务
3.  兼容ROS/ROS2，支持仿真与真实机器人部署
4.  提供Python3.8适配版本，已集成至odin-nav-stack导航栈中
