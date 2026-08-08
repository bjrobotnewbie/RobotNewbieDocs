# rviz

RViz 是 ROS 2 的三维机器人可视化工具，用于查看机器人状态、传感器数据、TF 和规划结果。

## 项目链接

- GitHub: <https://github.com/ros2/rviz>

## 项目概述

RViz 是 ROS 生态中最核心的调试和可视化工具之一。ROS 2 版本包含在主 `ros2.repos` 中，支持显示 Axes、Grid、Robot Model、TF、Laser Scan、Point Cloud、Image、Marker、Odometry、Pose、Map 等大量机器人数据类型，并提供相机视角、选择、测量、导航目标、交互标记等工具。

它不是算法库，而是机器人开发过程中的“观察窗口”。开发者可以用 RViz 检查 URDF 模型、坐标系关系、传感器输出、导航地图、SLAM 结果、运动规划轨迹和控制状态，从而快速定位 ROS 系统中的数据、配置或算法问题。
