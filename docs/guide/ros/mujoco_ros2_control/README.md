# mujoco_ros2_control

为 MuJoCo 物理模拟器提供了一个 ROS 2 控制硬件接口，包含适配各类传感器、RGB-D 相机和激光雷达的插件。

## 项目链接

- GitHub: <https://github.com/ros-controls/mujoco_ros2_control>
- 项目主页: https://control.ros.org/rolling/doc/mujoco_ros2_control/doc/index.html

## 项目概述

## 项目介绍
本项目是针对MuJoCo物理模拟器的ROS 2控制硬件接口，将MuJoCo封装为硬件/系统接口，可让ros2_control栈（控制器管理器、各类控制器、控制器接口）对接基于MJCF或URDF生成的仿真机器人。项目包含核心系统接口插件、消息服务定义、扩展插件、示例demo、测试套件以及Docker运行配置等子包。

## 主要特性
1.  完整适配ros2_control的MuJoCo系统接口插件
2.  支持MJCF/URDF格式模型的转换工具，可自动生成MuJoCo仿真模型
3.  可选插件系统，支持自定义发布器与服务来扩展仿真能力
4.  提供基础控制、PID和传动配置的示例演示程序
5.  适配ROS 2 Humble、Iron、Jazzy、Rolling等多个发行版，通过CI持续集成测试
