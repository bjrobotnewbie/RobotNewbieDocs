# ros-bridge

用于CARLA模拟器的ROS桥接

## 项目链接

- GitHub: <https://github.com/carla-simulator/ros-bridge>

## 项目概述

## 项目介绍
本项目是CARLA模拟器的ROS/ROS2桥接包，可实现ROS与CARLA之间的双向通信：将CARLA服务器的信息转换为ROS话题数据，同时将ROS节点间发送的指令转换为可在CARLA中执行的操作。本版本适配CARLA 0.9.13。

## 主要特性
1.  传感器数据转换：支持激光雷达、语义激光雷达、深度/分割/RGB/DVS相机、GNSS、雷达、IMU等传感器数据转为ROS话题
2.  目标与环境数据输出：提供tf坐标变换、交通灯状态、可视化标记、碰撞检测、车道入侵检测等数据
3.  自动驾驶Agent控制：支持转向、油门、刹车控制
4.  仿真环境控制：可启停仿真、修改仿真参数

完整安装与使用文档可查看官方文档链接。
