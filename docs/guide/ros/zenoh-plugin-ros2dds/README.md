# zenoh-plugin-ros2dds

适用于ROS2、基于DDS RMW的Zenoh插件。如需了解相较于其他DDS RMW实现使用本插件的优势，参见：https://discourse.ros.org/t/ros-2-alternative-middleware-report/

## 项目链接

- GitHub: <https://github.com/eclipse-zenoh/zenoh-plugin-ros2dds>
- 项目主页: https://zenoh.io

## 项目概述

## 项目介绍
本项目是针对ROS2的Zenoh插件，可作为DDS RMW实现，通过Zenoh转发ROS2的DDS通信流量。Zenoh是一款零开销的发布订阅、存储查询与计算框架，可统一整合动态数据、静态数据与计算任务。

该插件提供了两种部署形式：作为Zenoh路由器加载的动态库`zenoh-plugin-ros2dds`，以及独立可执行程序`zenoh-bridge-ros2dds`。它可以帮助机器人应用解决无线连接、带宽占用和跨系统集成的通信问题。

## 主要特性
1.  更好适配ROS生态：完整支持ROS话题、服务、动作，兼容`ros2`、`rviz2`等官方工具
2.  简化配置：可统一在桥接器上配置ROS命名空间，无需修改每个ROS节点
3.  原生集成Zenoh应用：ROS服务和动作可映射为Zenoh可查询对象
4.  高效发现机制：桥接器间的发现信息传输更紧凑
5.  完整覆盖ROS通信链路：可替代原生DDS中间件实现ROS2全场景通信
