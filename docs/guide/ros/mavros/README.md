# mavros

MAVROS 是 MAVLink 与 ROS 之间的可扩展通信节点和网关，常用于无人机和地面站系统集成。

## 项目链接

- GitHub: <https://github.com/mavlink/mavros>

## 项目概述

MAVROS 将 MAVLink 飞控通信协议接入 ROS/ROS 2，使 PX4、ArduPilot 等飞控系统可以通过 ROS topic、service 和 plugin 机制与上层算法交互。仓库包含 mavros 主包、mavros_extras、mavros_msgs 等多个包，并长期维护 MAVLink 版本、坐标系转换、地理坐标和不同 ROS 发行版支持。

它适合无人机自主飞行、地面站桥接、任务控制、状态监控、传感器/定位信息转发和飞控与机器人算法融合。对于需要在 ROS 中控制飞控、读取状态、发送航点或集成视觉/规划算法的无人机项目，MAVROS 是最常用的基础组件之一。
