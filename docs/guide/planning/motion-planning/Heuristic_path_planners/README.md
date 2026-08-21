# Heuristic_path_planners

包含类与函数集合，支持基于启发式算法（如 A*、Theta* 和 LazyTheta*）的 2D/3D 路径规划，并提供 ROS 接口。

## 项目链接

- GitHub: <https://github.com/robotics-upo/Heuristic_path_planners>

## 项目概述

## 项目介绍
该项目是一个启发式路径规划算法集合，提供A*、Theta*、LazyTheta*等算法的纯C++实现，同时附带ROS接口，可以在ROS网络中快速部署运行这些路径规划算法，支持2D和3D路径生成。项目兼容Ubuntu 18.04+ROS Melodic以及Ubuntu 20.04+ROS Noetic环境，处于持续开发中。

## 主要特性
1.  实现多种经典启发式路径规划算法，覆盖2D和3D路径规划场景
2.  低依赖的纯C++核心实现，同时提供完整ROS集成方案
3.  提供官方编译与运行demo教程，支持通过debian包或源码编译安装
4.  附带示例地图与测试脚本，可快速启动演示节点发起路径规划请求
