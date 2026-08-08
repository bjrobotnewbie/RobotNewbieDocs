# unitree_ros

- 项目链接：https://github.com/unitreerobotics/unitree_ros

## 项目概述

这是宇树机器人的 ROS 仿真包，你可以在 Gazebo 中加载机器人和关节控制器，对机器人关节进行低级控制（控制扭矩、位置和角速度）。

需要注意的是，Gazebo 仿真不能进行高级控制（如行走）。除了这些仿真功能，你还可以结合 `unitree_ros_to_real` 包在 ROS 中控制真实机器人，对于真实机器人，可以使用 ROS 包进行高级和低级控制。

包含的包：
- **机器人描述**：支持 A1、A2、Aliengo、B1、B2、Go1、Go2、G1、H1、H2、Laikago、R1、Z1 等多种宇树机器人模型
- **机器人和关节控制器**：unitree_controller、z1_controller
- **仿真相关**：unitree_gazebo、unitree_legged_control

需要 ROS Melodic 或 Kinetic 和 Gazebo8，依赖 unitree_legged_msgs。
