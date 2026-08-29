# ROS

ROS Noetic 两轮差速自主移动机器人：ESP32 底盘（PID/编码器/IMU）+ J1900 车载平台（LiDAR/相机）+ PC（SLAM/导航/人体跟随），三机分布式全链路开源实现

## 项目链接

- GitHub: <https://github.com/lawliet206/ROS>
- 项目主页: <https://github.com/lawliet206/ROS/blob/main/docs/ARCHITECTURE.md>

## 项目介绍
本项目是基于ROS Noetic的两轮差速自主移动机器人开源平台，采用三机分布式架构：ESP32负责底盘PID控制、编码器与IMU数据采集；J1900车载端负责LiDAR、相机数据采集与转发；PC端运行SLAM、导航、人体跟随等核心算法。覆盖从电机控制到上层应用的全链路开源实现，可复现可扩展。

## 主要特性
1.  **完整功能栈**：支持gmapping SLAM建图、AMCL+move_base+TEB自主导航、多点巡航、视觉+雷达融合人体跟随、robot_localization的EKF里程计与IMU融合
2.  **分布式架构**：通过WiFi和USB实现PC、J1900、ESP32三级通信，数据流转清晰稳定
3.  **配套仿真**：提供Gazebo差速机器人仿真环境与同款导航栈
4.  适配Ubuntu20.04与ROS Noetic，已完成实机验证
