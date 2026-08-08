# go2_ros2_sdk

宇树Unitree GO2 AIR/PRO/EDU 的非官方 ROS2 SDK 支持包

## 项目链接

- GitHub: <https://github.com/abizovnuralem/go2_ros2_sdk>

## 项目概述

## 项目介绍
本项目是Unitree GO2 AIR/PRO/EDU四足机器人的非官方ROS2 SDK，支持通过Wi-Fi（WebRTC协议）和以太网（CycloneDDS协议）实现机器人与ROS2的连接，可将机器人数据接入ROS2生态。项目已完成重构，激光雷达数据流帧率从2Hz提升至7Hz，适配固件v1.1.7。

## 主要特性
1.  支持URDF模型、实时同步关节状态、IMU数据、足端力传感器数据
2.  提供实时相机、激光雷达点云/激光扫描话题数据，支持Foxglove桥接
3.  支持手柄控制、多机器人连接，可实现点云地图构建与存储
4.  集成SLAM（slam_toolbox）、导航（nav2）与目标检测（coco）功能
5.  兼容Ubuntu22.04+Python3.10，支持Linux/Windows系统，通过ROS2构建验证
