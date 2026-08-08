# rclcpp

rclcpp 是 ROS 2 的 C++ 客户端库，提供编写 ROS 2 C++ 节点的标准 API。

## 项目链接

- GitHub: <https://github.com/ros2/rclcpp>

## 项目概述

rclcpp 包含 ROS 2 标准安装中的 C++ 客户端库源码，是 C++ 开发者与 ROS 2 系统交互的主要入口。通过 `rclcpp/rclcpp.hpp`，用户可以创建节点、发布和订阅 topic、编写 service/client、使用 timers、parameters、executors、logging、QoS 和时间等 ROS 2 基础能力。

该项目位于 ROS 2 中间件抽象之上，是大多数 C++ ROS 2 包的基础依赖。对于机器人系统工程，rclcpp 决定了节点生命周期、回调调度、通信语义和性能特性，因此既适合应用开发者日常使用，也适合框架和工具作者深入理解 ROS 2 的 C++ 编程模型。
