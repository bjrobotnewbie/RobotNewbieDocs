# open_mower_ros

## 项目链接

- GitHub: <https://github.com/ClemensElflein/open_mower_ros>

## 项目概述

## 项目介绍
open_mower_ros 是用于控制OpenMower的ROS工作空间，基于ROS Noetic开发，用于实现自动割草机器人的控制。项目依赖多个第三方库：基于Slic3r的割草路径规划器slic3r_coverage_planner、支持避障与路径跟踪的本地规划器teb_local_planner，以及xESC电机控制器的ROS接口xesc_ros。

项目提供两种Docker镜像版本：适配OpenMower OS v2的标准版镜像，依赖宿主机提供web和MQTT服务；适配旧版OpenMower OS v1的legacy镜像，内置nginx和mosquitto提供相关服务。

## 主要特性
1.  集成专业的覆盖式割草路径规划功能
2.  支持基于运动学约束的本地避障与路径跟踪
3.  适配多款开源硬件电机控制器
4.  提供标准化的Docker部署方案，区分新旧系统版本
5.  支持通过roslaunch快速启动完整割草控制系统
