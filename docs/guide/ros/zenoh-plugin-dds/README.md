# zenoh-plugin-dds

一个支持透明路由DDS数据的zenoh插件。DDS应用可通过该插件借助zenoh实现地理路由或更具可扩展性的发现服务。针对ROS2机器人应用，请使用：https://github.com/eclipse-zenoh/zenoh-plugin-ros2dds

## 项目链接

- GitHub: <https://github.com/eclipse-zenoh/zenoh-plugin-dds>

## 项目概述

## 项目介绍
这是Eclipse Zenoh的DDS插件，可透明路由DDS数据，帮助DDS应用借助Zenoh实现地理路由或优化发现扩展。它基于DDS标准，可有限兼容ROS 2，但官方推荐ROS 2用户使用专用的`zenoh-plugin-ros2dds`插件以获得更好的集成体验。

## 主要特性
1.  实现DDS与Zenoh的数据透明互通，支持地理化路由与发现扩展
2.  可编译为Zenoh插件或独立的`zenoh-bridge-dds`工具
3.  针对ROS 2场景存在专用替代插件，可更好适配ROS图、ROS工具链，支持ROS命名空间配置，优化服务与动作通信效率
4.  采用EPL-2.0/Apache 2.0双开源协议
