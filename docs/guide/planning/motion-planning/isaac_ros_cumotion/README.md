# isaac_ros_cumotion

用于机械臂运动规划与控制的NVIDIA加速包

## 项目链接

- GitHub: <https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_cumotion>
- 项目主页: https://developer.nvidia.com/isaac-ros-gems

## 项目概述

## 项目介绍
Isaac ROS cuMotion是NVIDIA推出的ROS 2机械臂运动规划与控制加速套件，通过CUDA加速实现机器人操作功能。它将cuMotion集成至MoveIt 2，可生成平滑无碰撞轨迹，同时通过ROS 2动作/服务暴露逆运动学和轨迹生成能力，还支持从深度数据流中分割过滤机器人本体。可搭配nvblox通过深度相机实现环境三维重建，基于符号距离场(SDF)完成障碍物感知规划。

## 主要特性
1.  **更优循环时长**：可生成带障碍物约束的最优时间平滑轨迹，复杂场景下也能生成有效规划，相比传统规划器缩短运动时间
2.  **更快规划速度**：依托CUDA加速，可在毫秒级内生成无碰撞最优轨迹
3.  **障碍物感知规划**：支持结合深度相机数据构建环境SDF地图，实现避障规划，同时可过滤机器人本体点云
4.  **高灵活性**：模块化设计可轻松适配现有ROS 2尤其是MoveIt 2工作流
