# Orion-Quadruped

🐕 Orion 是一款由 ROS2 驱动的、具有 12 自由度四足机器人的狗狗，我亲手设计、构建并编程。

## 项目链接

- GitHub: <https://github.com/AshishA26/Orion-Quadruped>

## 项目介绍
Orion是一款从零开发的12自由度四足机器狗，基于ROS2构建，耗时8个月完成。硬件上采用NVIDIA Jetson Orin Nano负责高层AI与感知，搭配定制STM32 PCB实现实时底层控制。支持LiDAR建图、自主导航、视觉感知等功能，还可通过强化学习在仿真环境中训练步态。

## 主要特性
1.  **ROS2与AI**：基于Jetson Orin Nano运行Isaac ROS Docker，通过TensorRT加速推理
2.  **感知能力**：搭载双CSI摄像头，支持MIDAS/SGBM立体深度估计与MediaPipe手部姿态识别
3.  **SLAM与自主导航**：搭配RPLIDAR A1M8，通过`slam_toolbox`和`nav2`实现建图与点击式纯追踪导航
4.  **底层控制**：自定义STM32 FreeRTOS固件，实现逆运动学、行走步态与IMU姿态稳定
5.  **定制硬件**：多层SMD PCB用于供电分配、舵机驱动与传感器接口
6.  **强化学习**：在NVIDIA Isaac Lab中通过PPO算法在平坦与崎岖地形环境中训练步态
7.  **交互展示**：通过Python/OpenCV节点驱动OLED屏幕实现表情动画
