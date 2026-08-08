# kiss-icp

- 项目链接：https://github.com/PRBonn/kiss-icp
- 项目主页：https://www.ipb.uni-bonn.de/wp-content/papercite-data/pdf/vizzo2023ral.pdf

## 项目概述

KISS-ICP (Keep It Simple, Sparse ICP) 是一个**开箱即用的激光雷达里程计流水线**，来自德国波恩大学 PRBonn 实验室，最大的特点就是**几乎不需要调参就能在大多数场景下正常工作**。

### 核心特点

- **零调参**：默认参数就能在大多数场景下工作，"it just works"
- **保持稀疏**：只保留有效点，不构建稠密地图，计算高效
- **跨平台**：支持 Linux、Windows、macOS
- **提供 ROS 2 封装**：方便集成到 ROS 2 导航系统
- **开源活跃**：持续维护更新，社区活跃

### 算法原理

KISS-ICP 基于经典的 ICP (Iterative Closest Point) 配准，但做了多个关键简化：
- 简单的配准流水线
- 稀疏深度积分保持地图稀疏
- 自适应退化解检测

### 支持功能

- 多传感器支持：支持多种激光雷达
- 里程计输出：提供位姿估计
- 地图保存：可以保存构建的点云地图
- C++ 核心，Python 绑定：方便在不同环境使用

KISS-ICP 是目前最受欢迎的开源激光雷达里程计之一，特别适合需要快速部署SLAM系统的场景。
