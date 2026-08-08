# openamr-platform-sw

OpenAMRobot 移动机器人平台的 ROS 2 软件、仿真、导航、停靠、控制、驱动及快速搭建（bringup）工具集

## 项目链接

- GitHub: <https://github.com/openAMRobot/openamr-platform-sw>

## 项目概述

## 项目介绍
本项目是面向OpenAMRobot移动机器人平台的ROS 2 Jazzy软件栈，提供机器人描述、Gazebo Harmonic仿真、Nav2导航、基于AprilTag包的自动对接（含停靠与离坞）功能。当前处于实验阶段，仿真端对接功能已完成端到端调优，实物机器人的驱动、控制与硬件集成开发正在进行中。项目还附带完整的ROS 2入门课程、开发者指南、故障排查等配套文档，完整产品包可从官方发布仓库下载。

## 主要特性
1.  基于ROS 2 Jazzy构建完整机器人软件栈
2.  支持Gazebo Harmonic仿真环境
3.  集成Nav2实现自主导航
4.  采用3个36h11家族（ID 0/1/2）的AprilTag实现高精度宽基线自动对接与离坞
5.  提供Docker与手动两种部署方式，适配不同开发场景
6.  附带ROS 2入门课程与全套开发、测试、版本管理文档
