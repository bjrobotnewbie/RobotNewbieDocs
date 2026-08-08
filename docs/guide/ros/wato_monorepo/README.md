# wato_monorepo

适用于WATonomous自动驾驶软件流水线的容器化ROS2栈

## 项目链接

- GitHub: <https://github.com/WATonomous/wato_monorepo>
- 项目主页: https://www.watonomous.ca/

## 项目概述

## 项目介绍
本项目是WATonomous自动驾驶车辆EVE的Docker化ROS2单代码仓库，用于搭建完整的自动驾驶软件栈。通过Docker实现环境一键部署，无需在本地主机安装额外依赖库，支持Ubuntu >=22.04、Windows WSL/WSL2以及MacOS系统，部分功能需要NVIDIA GPU支持。项目所需的大体积文件如模型权重、地图、rosbag录制包需从团队专属Google Drive下载并放置到对应目录。

## 主要特性
1.  模块化架构，包含基础设施、硬件交互、感知、世界建模、决策规划、仿真六大功能模块
2.  内置CARLA仿真环境支持，可脱离实车进行开发测试
3.  集成Foxglove桥接与数据流工具，方便数据可视化与调试
4.  提供完整的硬件对接能力，可直接连接车辆传感器与整车硬件
