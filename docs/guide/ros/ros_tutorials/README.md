# ros_tutorials

ROS wiki 上教程所用的代码

## 项目链接

- GitHub: <https://github.com/ros/ros_tutorials>
- 项目主页: http://wiki.ros.org/ros_tutorials

## 项目概述

## 项目介绍
`ros_tutorials`是配套ROS 2官方文档的教程代码集合，用于在入门教程中讲解ROS 2核心概念，包括节点、话题、服务、动作、参数和launch文件。本分支适配ROS 2 Rolling Ridley版本，其他ROS发行版请切换对应仓库分支。

本仓库包含两个包：
1.  `turtlesim`：基于Qt开发的轻量级模拟器，是ROS 2入门教学的经典工具
2.  `turtlesim_msgs`：定义`turtlesim`使用的消息、服务和动作的接口包

## 主要特性
1.  **turtlesim功能**：可在窗口中绘制并操控一只或多只乌龟，支持通过ROS 2话题、服务、动作实现移动、生成新乌龟、修改画笔颜色等操作，内置`turtlesim_node`模拟器窗口、键盘遥控节点、画正方形节点、模仿运动节点，还提供多实例启动launch文件。
2.  **turtlesim_msgs**：定义了`Color`、`Pose`等消息，`Kill`、`Spawn`等服务，以及`RotateAbsolute`动作的接口定义。
3.  配套官方ROS 2入门教程，覆盖节点、话题等核心ROS 2概念教学。
