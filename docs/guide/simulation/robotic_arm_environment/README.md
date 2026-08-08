# robotic_arm_environment

适用于强化学习的Doosan机械臂在Gazebo与ROS2中的仿真、控制与可视化。

## 项目链接

- GitHub: <https://github.com/dvalenciar/robotic_arm_environment>

## 项目概述

## 项目介绍
本项目基于ROS 2 Jazzy和Gazebo Harmonic，从零搭建了6自由度斗山（Doosan a0912/m1013）机械臂的仿真环境，支持自定义强化学习（RL）算法测试，可实现机械臂抓取随机位置绿色目标球的reach任务。项目已从老旧的ROS 2 Foxy+Gazebo Classic版本迁移至最新适配Ubuntu 24.04的技术栈。

## 主要特性
1.  完整的机械臂仿真流程，包含机器人URDF描述、Gazebo仿真环境配置与ros2_control控制器
2.  支持独立启动机械臂、目标球，或完整的RL训练环境
3.  提供随机动作测试脚本，可快速验证环境运行效果
4.  附带RViz可视化与关节控制工具，支持调试机械臂模型

适配环境为Ubuntu 24.04 + ROS 2 Jazzy，可通过官方apt源快速安装依赖，部署流程简洁。
