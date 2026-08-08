# rl_sar

机器人强化学习算法的仿真验证与实物部署，适用于四足机器人、轮式机器人及人形机器人。"sar"代表"simulation and real"。

## 项目链接

- GitHub: <https://github.com/fan-ziqi/rl_sar>

## 项目概述

## 项目介绍
rl_sar是一个用于机器人强化学习算法的仿真验证与实物部署框架，其中sar代表"simulation and real"，支持四足机器人、轮式机器人、人形机器人。该框架兼容ROS Noetic、ROS2 Foxy/Humble，支持Gazebo、Mujoco、IsaacGym、IsaacSim仿真环境，以及libtorch和onnxruntime推理引擎，可运行于Linux和仅支持Mujoco仿真的macOS系统，支持运动控制和舞蹈两类任务。

## 主要特性
1.  支持多机器人平台：包含Unitree全系列机器人、FFTAI人形机器人、智瑙L4W4、Deeprobotics-Lite3、Agibot-D1等多款机型，部分机型提供预训练策略
2.  适配多种仿真与部署环境：兼容主流机器人仿真工具与ROS版本，支持实物真机部署
3.  提供Python版本v2.3长期维护分支，当前Python版本暂停止维护
4.  配套有相关讨论社区与依赖项目指引
