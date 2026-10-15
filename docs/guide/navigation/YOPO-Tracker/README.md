# YOPO-Tracker

无人机端到端敏捷跟踪与导航方法

## 项目链接

- GitHub: <https://github.com/TJU-Aerial-Robotics/YOPO-Tracker>

## 项目介绍
YOPO-Tracker是面向无人机的端到端敏捷跟踪与导航方法，对应论文为《YOPOv2-Tracker: An End-to-End Agile Tracking and Navigation Framework》，基于ROS、Unity仿真器实现，适配Ubuntu 24.04与Jetson Orin NX平台，支持无人机对移动目标的跟踪任务，提供预训练模型与仿真环境，可直接测试跟踪策略。

## 主要特性
1. 端到端设计，简化无人机跟踪导航流程；
2. 适配ROS2与Conda环境，支持Jetson Orin NX硬件部署；
3. 提供预构建Unity仿真器，包含控制器、动力学仿真模块及ROS-TCP连接组件；
4. 预训练模型可实现对0-6m/s移动目标的跟踪，支持FPV视角与第三方视角的跟踪效果可视化；
5. 支持人类与无人机对抗的FPS游戏式仿真场景，便于算法验证与数据采集。
