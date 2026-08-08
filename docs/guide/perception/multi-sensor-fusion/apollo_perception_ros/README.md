# apollo_perception_ros

基于ROS中Apollo r3.0.0感知模块的目标检测/跟踪/融合

## 项目链接

- GitHub: <https://github.com/cedricxie/apollo_perception_ros>

## 项目概述

## 项目介绍
本项目是Apollo 3.0.0感知模块的ROS移植版本，将Apollo的障碍物感知模块提取并修改为可作为标准ROS节点运行的程序，解决了原生Apollo依赖定制化ROS环境、后续版本切换至Cyber RT无法兼容常规ROS工具的问题。项目面向学习自动驾驶感知架构的学生、研究者，需要在ROS中测试多传感器感知流水线的开发者，以及适配 legacy Apollo感知代码用于教学或仿真的维护者。2026年起重新维护，当前为历史教育向移植项目，非生产级自动驾驶栈。

## 主要特性
1.  基于Apollo r3.0.0感知模块实现目标检测、跟踪与融合
2.  完全兼容标准ROS工作流，可使用ROS原生工具链
3.  提供完整的Docker运行环境
4.  支持LiDAR、相机及多传感器融合感知管线

已知限制：需要旧版软件栈（Ubuntu 14.04、CUDA 8），部分雷达包支持不完全，现代GPU可能需要重新编译CUDA工件。
