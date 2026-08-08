# Universal_Robots_ROS2_Driver

Universal Robots ROS2 Driver 是面向 UR 协作机器人全系列的 ROS 2 驱动，支持 CB3、e-Series 和 PolyScope X 控制器。

## 项目链接

- GitHub: <https://github.com/UniversalRobots/Universal_Robots_ROS2_Driver>

## 项目概述

该驱动是较早的 ROS 2 机械臂驱动之一，基于 Universal_Robots_Client_Library 开发，支持 UR 机器人在 ROS 2 中进行控制和状态交互。它提供 standalone 启动方式，也可与 MoveIt 2 结合使用，并利用 ROS 2 带来的低延迟、安全性和中间件配置灵活性。

驱动覆盖 UR 从 3kg 到 30kg 负载的整条产品线，支持急停/安全停止状态处理、自动速度缩放、示教器手动速度缩放，以及通过 externalControl URCap 将 ROS 2 行为纳入机器人程序。它适合工业协作机器人应用、研究实验、MoveIt 2 规划执行和真实 UR 机械臂系统集成。
