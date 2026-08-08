# stretch_ros2

- 项目链接：https://github.com/hello-robot/stretch_ros2
- 项目主页：https://docs.hello-robot.com/0.3/ros2/getting_started/

## 项目概述

stretch_ros2 是 Hello Robot Inc. 公司 **Stretch 移动机械臂**的官方 ROS 2 软件包，提供完整的 ROS 2 Humble 支持。

Stretch 是一款专为研究和人机交互设计的低成本移动 manipulator，具有很好的安全性和可访问性。

### 包含的包

- **stretch_calibration**：生成校准后的 URDF 模型
- **stretch_core**：Stretch 的 ROS 2 驱动
- **stretch_deep_perception**：使用开源深度学习模型进行环境感知的演示
- **stretch_demos**：简单自主操作演示
- **stretch_description**：Stretch 机器人描述文件（URDF）
- **stretch_funmap**：FUNMAP（Fast Unified Navigation, Manipulation And Planning）演示
- **stretch_nav2**：集成 Nav2 导航栈，包含 slam_toolbox、AMCL 等
- **stretch_octomap**：使用 OctoMap 进行建图
- **stretch_rtabmap**：使用 RTAB-Map 进行 SLAM

### 主要特点

- 完整 ROS 2 驱动支持
- 提供建图、导航、操作全套功能
- 丰富的演示代码方便入门
- 活跃维护，文档完善

stretch_ros2 是使用 Stretch 移动机械臂进行研究开发的基础软件包。
