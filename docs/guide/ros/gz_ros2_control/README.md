# gz_ros2_control

gz_ros2_control 是连接 Gazebo Sim 与 ros2_control 控制架构的 ROS 2 包。

## 项目链接

- GitHub: <https://github.com/ros-controls/gz_ros2_control>
- 项目主页: https://gazebosim.org

## 项目概述

gz_ros2_control 提供 Gazebo Sim system plugin，用于在 Gazebo 模型中实例化 ros2_control controller manager，并把仿真模型与 ROS 2 控制器连接起来。它让用户可以在 Gazebo 中使用与真实机器人相同或相近的 ros2_control 控制接口，从而进行控制器开发、测试和仿真验证。

项目维护 ROS 2 与 Gazebo 不同发行版之间的兼容矩阵，例如 Rolling/Jetty、Jazzy/Harmonic、Humble/Fortress 等。它适合需要在 Gazebo 中测试机器人硬件接口、控制器、关节命令和状态反馈的开发者，是 ROS 2 控制仿真闭环中的关键桥梁。
