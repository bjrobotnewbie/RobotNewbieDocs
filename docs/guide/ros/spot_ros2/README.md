# spot_ros2

spot_ros2 是 Boston Dynamics Spot 机器狗的 ROS 2 驱动包集合，桥接 Spot SDK 与 ROS 2。

## 项目链接

- GitHub: <https://github.com/rai-opensource/spot_ros2>

## 项目概述

spot_ros2 基于 ROS 1 版本 spot_ros 发展而来，提供与 Boston Dynamics Spot 交互所需的 ROS 2 包。核心 spot_driver 将 Spot SDK 的功能暴露为 ROS 2 topic、service 和 action，使用户可以控制 Spot、接收机器人状态、图像和其他传感信息，并在 ROS 2 系统中集成 Spot 的移动能力。

项目面向 Ubuntu 22.04 和 ROS 2 Humble，支持 ARM64 和 AMD64 平台，并与特定版本 spot-sdk 对应。它适合使用 Spot 做自主巡检、感知导航、远程操作、机器人研究和 ROS 2 算法集成的团队，提供了从工作空间安装到驱动运行的基础软件层。
