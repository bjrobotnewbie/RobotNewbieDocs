# cyclo_lab

此仓库提供了使用ROBOTIS机器人进行强化学习与模仿学习的教程，并支持Sim2Real功能，可将训练得到的策略部署到实体机器人上。

## 项目链接

- GitHub: <https://github.com/ROBOTIS-GIT/cyclo_lab>

## 项目概述

## 项目介绍
cyclo_lab是基于Isaac Lab的科研型仓库，用于在仿真环境中开展Robotis机器人的强化学习(RL)和模仿学习(IL)实验，支持Sim2Real功能，可以将训练好的策略部署到实体机器人上。项目依托NVIDIA Isaac Sim的GPU加速物理引擎与Isaac Lab的模块化RL流程，提供了适配Robotis硬件的仿真环境、配置工具与任务定义。当前依赖IsaacLab v2.2.0及以上版本，适配Ubuntu22.04、Python3.11环境，采用Apache2.0开源协议。

## 主要特性
1.  提供Docker一键部署环境，预装Isaac Sim 5.1.0、Isaac Lab v2.3.0及所有依赖
2.  内置适配Robotis机器人的仿真任务示例，如OMY Reach、OMY Lift等RL训练任务
3.  支持仿真到实体机器人的策略迁移，完成从Sim2Sim到Sim2Real的全流程实验
4.  模块化的RL训练流程，可快速配置与开展机器人学习实验
