# zed-ros2-wrapper

- 项目链接：https://github.com/stereolabs/zed-ros2-wrapper
- 项目主页：https://www.stereolabs.com/docs/ros2/

## 项目概述

这是 Stereolabs ZED 深度相机的 ROS 2 封装包，让你可以在 ROS 2 生态系统中使用 ZED 相机获取深度数据、彩色图像、点云等。

该包提供对多种数据类型的访问，包括：
- 校正和未校正的彩色和灰度图像
- 深度数据
- 彩色 3D 点云
- 定位和建图，可选 GNSS 数据融合
- 传感器数据
- 检测到的物体
- 人体骨骼数据
- 更多功能

主要特点：
- 支持多个 ROS 2 版本（Foxy、Humble、Jazzy）
- 支持多个 Ubuntu 版本（20.04、22.04、24.04）
- 需要 ZED SDK 和 CUDA 支持
- 使用 colcon 构建

该包已从 IntelRealSense 组织迁移到 stereolabs 组织，持续维护更新，是 ROS 中使用 ZED 相机的标准驱动包。
