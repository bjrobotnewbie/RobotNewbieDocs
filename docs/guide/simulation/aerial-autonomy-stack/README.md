# aerial-autonomy-stack

- 项目链接：https://github.com/JacopoPan/aerial-autonomy-stack
- 项目主页：https://arxiv.org/abs/2602.07264

## 项目概述

Aerial autonomy stack (AAS) 是一个一体化软件栈，用于多无人机自主飞行开发、仿真和部署，基于 ROS2、PX4/ArduPilot、YOLO、激光雷达和 NVIDIA Jetson。

主要功能：
1. **开发**：多无人机自主飞行，基于 ROS2，支持 PX4 和 ArduPilot
2. **仿真**：比实时更快的感知和控制仿真，支持 YOLO 和 3D LiDAR
3. **部署**：可部署到真实无人机，基于 JetPack、DeepStream 和 NVIDIA Orin

主要特点：
- 支持 PX4 和 ArduPilot 多飞行器仿真（四旋翼和 VTOL）
- 基于 ROS2 动作的自动驾驶仪接口（通过 XRCE-DDS 或 MAVROS）
- YOLO（ONNX GPU Runtime）和 LiDAR 里程计（KISS-ICP）
- 基于感知的仿真 3D 世界
- 支持可步进 Gymnasium 环境，比实时更快，多实例仿真
- Docker 化仿真，基于 Ubuntu CUDA
- Docker 化部署，基于 NVIDIA JetPack 和 DeepStream
- 支持 Windows 11（通过 WSL）
- 多 Jetson 在环仿真（HITL）测试 NVIDIA 和 ARM 机载计算

这是一个完整开放的无人机集群感知自主仿真与部署框架。
