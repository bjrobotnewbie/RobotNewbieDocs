# diffbot

DiffBot 是一款基于 ROS Noetic 和 Raspberry Pi 4 B 的自主双轮驱动（2WD）机器人。它配备 SLAMTEC 激光雷达和 ROS 控制硬件接口，能够利用 ROS 导航栈在未知环境中导航，并通过 SLAM 算法生成环境地图。

## 项目链接

- GitHub: <https://github.com/ros-mobile-robots/diffbot>
- 项目主页: <https://ros-mobile-robots.com>

## 项目介绍
DiffBot是一款基于ROS Noetic的自主两轮差速驱动机器人，以树莓派4 B为核心处理单元，搭载SLAMTEC激光雷达，支持ROS Navigation栈与SLAM算法，可实现未知环境建图与自主导航。本项目包含ROS驱动包、真实机器人的ROS Control硬件接口，以及DiffBot的仿真配置，配套有3D打印的模块化底座，支持多种相机模块与树莓派、Nvidia Jetson Nano等单板计算机。

## 主要特性
1. 基于ROS Noetic与树莓派4 B的自主差速驱动机器人
2. 集成SLAMTEC激光雷达，支持ROS Navigation栈与SLAM算法，可完成环境建图与自主导航
3. 提供真实机器人的ROS Control硬件接口及Gazebo仿真配置
4. 配套3D打印模块化底座，兼容多种相机模块，支持树莓派、Nvidia Jetson Nano等单板计算机
