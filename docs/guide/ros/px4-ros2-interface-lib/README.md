# px4-ros2-interface-lib

使用 ROS 2 通过计算机伙伴与 PX4 库进行接口

## 项目链接

- GitHub: <https://github.com/Auterion/px4-ros2-interface-lib>

## 项目概述

## 项目介绍
本项目是`px4-ros2-interface-lib`，用于在 companion computer 上通过 ROS 2 与 PX4 进行交互。它提供工具链支持编写动态注册到 PX4 的外部模式，可实现从高层导航任务到直接执行器控制的各类 setpoint 发送。项目基于 C++ 开发，同时提供未完全完善的 Python 绑定。

## 主要特性
1.  支持编写与 PX4 原生行为一致的外部模式，可发送多类型飞行控制 setpoint
2.  基于 PX4 的 uORB 消息实现交互，需保证 ROS 2 侧消息定义匹配
3.  提供 C++ 与 Python 两种开发接口，附带示例代码
4.  提供多种兼容性适配方案：使用最新版 PX4 与 px4_msgs、通过消息转换节点兼容不同版本消息，或使用对应 PX4 版本的 release 分支

使用场景：基于 ROS 2 的无人机外部自定义飞行模式开发，适用于需要扩展 PX4 原生飞行模式的 companion computer 开发项目。
