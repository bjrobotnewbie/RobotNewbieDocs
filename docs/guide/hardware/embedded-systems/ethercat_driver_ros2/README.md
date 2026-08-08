# ethercat_driver_ros2

用于将EtherCAT模块与ros2_control集成的硬件接口

## 项目链接

- GitHub: <https://github.com/ICube-Robotics/ethercat_driver_ros2>
- 项目主页: https://icube-robotics.github.io/ethercat_driver_ros2/

## 项目概述

## 项目介绍
本项目是一款适配`ros2_control`的EtherCAT硬件接口驱动，基于IgH EtherCAT Master for Linux开发，用于快速集成EtherCAT模块到ROS 2机器人开发流程中。EtherCAT是成熟的工业实时通信标准，该驱动通过参数文件即可完成硬件接口的配置与组装，简化了基于EtherCAT模块的ROS 2应用开发与部署流程。

## 主要特性
1.  实现了与`ros2_control`的标准硬件接口兼容
2.  基于通用参数化方式配置EtherCAT模块
3.  依托成熟的IgH EtherCAT Master实现可靠实时通信
4.  支持快速集成各类EtherCAT工业模块
5.  提供完整官方文档支持开发
