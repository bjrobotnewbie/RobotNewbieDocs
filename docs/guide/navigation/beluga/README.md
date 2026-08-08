# beluga

C++17 实现的通用蒙特卡洛局部化（MCL）算法实现，以及适用于 ROS 1 和 ROS 2 的 ROS 包。

## 项目链接

- GitHub: <https://github.com/Ekumen-OS/beluga>
- 项目主页: <https://ekumen-os.github.io/beluga/>

## 项目概述

## 项目介绍
Beluga是一个基于C++17开发的通用蒙特卡洛定位（MCL）算法实现库，同时提供可兼容ROS 1和ROS 2的ROS包。它可用于机器人自主定位场景，已在Turtlebot 2、Andino等多款机器人上完成运行演示。

## 主要特性
1.  采用正交组件的模块化设计，扩展性强
2.  高测试覆盖率，有效防止功能退化、便于代码迭代优化
3.  支持半自动化基准测试，可验证不同算法配置效果
4.  同时提供ROS无关的纯算法库与ROS集成包，适配多ROS版本
