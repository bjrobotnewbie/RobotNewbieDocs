# franka_ros2

franka_ros2 是 Franka Robotics 研究型机械臂的 ROS 2 集成包，基于 libfranka 提供控制接口。

## 项目链接

- GitHub: <https://github.com/frankarobotics/franka_ros2>
- 项目主页: https://frankarobotics.github.io/docs/franka_ros2/docs/index.html

## 项目概述

franka_ros2 让 Franka 研究机器人能够在 ROS 2 框架中被高效控制。它集成 libfranka，并提供构建、Docker 环境、测试和故障排查说明，帮助研究人员在 ROS 2 中连接和控制 Franka 机械臂。项目强调 Docker 方式可减少依赖冲突并保证可复现构建环境。

该包处于快速开发中，适合机器人研究团队、力控/阻抗控制实验、机械臂操作算法、MoveIt 2 集成和 Franka 平台应用开发。由于 Franka 机械臂对实时性和网络配置有要求，README 也包含 UDP timeout 等常见问题排查入口。
