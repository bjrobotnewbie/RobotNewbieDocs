# Universal_Robots_ROS2_Description

- 项目链接：https://github.com/UniversalRobots/Universal_Robots_ROS2_Description

## 项目概述

这是**优傲机器人（Universal Robots）**官方维护的 ROS2 项目，包含了优傲各系列机械臂的描述文件（URDF）和碰撞网格模型。

### 支持的机械臂型号

- UR3
- UR5 / UR5e
- UR10 / UR10e
- UR16e
- UR20e
- UR30e

所有型号都提供了：
- **URDF 模型**：完整的机器人描述，包括连杆、关节、传动等
- **碰撞网格**：用于碰撞检测的简化网格
- **可视化网格**：用于 RViz 可视化的高精度网格

### 兼容性

支持主流 ROS2 发行版：
- Humble
- Iron
- Jazzy
- Kilted
- Rolling

这个包是优傲机器人在 ROS2 中进行仿真、规划和控制的基础依赖，被广泛使用在 ROS2 机器人开发中。
