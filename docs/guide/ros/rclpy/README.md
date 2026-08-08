# rclpy

- 项目链接：https://github.com/ros2/rclpy

## 项目概述

rclpy 是 ROS 2 官方的 **Python 语言客户端库**，是 ROS 2 Python API 的底层实现，所有 Python 编写的 ROS 2 节点都依赖这个库。

rclpy 基于 ROS 2 的 C 底层客户端库 (rcl) 提供 Python 绑定，让开发者可以用 Python 快速编写 ROS 2 节点。

### 主要功能

- 提供 Python API 访问 ROS 2 核心功能
- 支持创建节点、发布者、订阅者、服务端、客户端
- 支持定时器、参数服务、TF2 等核心 ROS 概念
- 支持多线程回调执行
- 提供文档生成，API 文档在线可访问

### 特点

- 官方维护：ROS 2 项目核心组成部分
- 稳定可靠：经过大量项目使用验证
- 持续更新：跟随 ROS 2 版本同步更新
- Pythonic API：符合 Python 开发习惯

作为 ROS 2 的官方 Python 客户端库，rclpy 是所有 Python ROS 2 开发的基础。
