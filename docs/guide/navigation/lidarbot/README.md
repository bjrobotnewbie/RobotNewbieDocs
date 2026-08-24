# lidarbot

使用 ROS2 Jazzy 运行在 Raspberry Pi 4 上的 Ubuntu Server 24.04 系统控制差分驱动机器人。该车辆配备用于视觉反馈的 Raspberry Pi 摄像头，以及用于同时定位与地图构建（SLAM）、自主导航和避障的 RPLIDAR A1 传感器。

## 项目链接

- GitHub: <https://github.com/TheNoobInventor/lidarbot>

## 项目概述

## 项目介绍
本项目是一款基于ROS2 Jazzy的差分驱动移动机器人，运行在搭载Ubuntu Server 24.04的树莓派4上。机器人配备树莓派摄像头、RPLIDAR A1激光雷达与MPU6050 IMU，可通过`robot_localization`包结合扩展卡尔曼滤波器(EKF)融合IMU与轮式编码器数据，获得高精度里程计。支持使用Nav2栈实现SLAM建图、自主导航与避障，同时适配Waveshare电机驱动板，通过`ros2_control`框架实现硬件控制与传感器数据广播。

## 主要特性
1.  基于ROS2 Jazzy构建，支持跨主机开发部署，同时提供ROS2 Humble分支
2.  集成多传感器融合方案，通过EKF优化里程计精度
3.  支持Gazebo仿真与实物机器人两种部署场景
4.  实现SLAM建图、自主导航、遥控操作、障碍物规避功能
5.  适配树莓派摄像头、RPLIDAR A1、MPU6050与Waveshare电机驱动板等主流硬件
