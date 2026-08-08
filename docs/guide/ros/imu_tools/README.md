# imu_tools

适用于IMU设备的ROS工具

## 项目链接

- GitHub: <https://github.com/CCNYRoboticsLab/imu_tools>

## 项目概述

## 项目介绍
这是一款面向ROS的IMU工具集，提供IMU相关的滤波与可视化功能，适配ROS1和ROS2全主流发行版。项目包含两款IMU数据融合滤波节点与一款RViz可视化插件，可将IMU的角速度、加速度计数据（可选磁力计数据）融合为设备姿态，还可在RViz中展示标准IMU消息。

## 主要特性
1.  **imu_filter_madgwick**：基于开源AHRS算法实现的IMU数据融合滤波，输出设备姿态
2.  **imu_complementary_filter**：采用互补融合方案的IMU滤波，输出姿态四元数
3.  **rviz_imu_plugin**：RViz插件，可可视化`sensor_msgs::Imu`消息
4.  支持二进制快速安装与源码编译安装，适配全ROS1、ROS2发行版
5.  滤波后的数据可配合robot_localization、FusionCore等工具实现多传感器融合位姿估计
