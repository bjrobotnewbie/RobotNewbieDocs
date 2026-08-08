# ros2_robotiq_gripper

## 项目链接

- GitHub: <https://github.com/PickNikRobotics/ros2_robotiq_gripper>

## 项目概述

## 项目介绍
本项目是针对Robotiq机械手的ROS 2驱动、控制器及描述功能包仓库，旨在支持多款Robotiq机械手，初始仅支持2f-85型号，同时欢迎社区提交PR以适配更多机型，官方另有独立的`ros2_epick_gripper`仓库支持e-pick机械手。
当前`main`分支适配ROS 2 Humble、Iron及Rolling版本，不保证严格的API/ABI兼容性，项目由社区维护，未获得Robotiq官方赞助。

## 主要特性
1.  提供ROS 2环境下的Robotiq机械手驱动、控制及URDF描述功能
2.  支持多型号Robotiq机械手扩展，初始适配2f-85
3.  主流ROS 2发行版均有对应构建支持，提供二进制与半二进制构建流水线
