# ros2-performance

- 项目链接：https://github.com/irobot-ros/ros2-performance

## 项目概述

这是 iRobot 提供的 ROS 2 性能评估框架，包含可执行文件和工具，可以轻松模拟任意 ROS 2 系统并测量其性能。系统拓扑可以在运行时使用 JSON 文件或命令行选项提供。

该框架跟踪以下性能指标：
- 延迟
- 可靠性
- CPU 使用率
- 内存使用率

核心完全使用 C++ 开发，除了 ROS 2 核心库之外没有外部依赖，这使得它非常易于编译，并且可以在嵌入式平台上使用。该框架主要用于评估单进程应用程序，虽然也能测量多进程应用性能，但不是所有指标都可用。

需要 ROS 2 Rolling，构建需要 Python 3、CMake 和 colcon。
