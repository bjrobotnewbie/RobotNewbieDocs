# MuJoCo-LiDAR

基于 MuJoCo 的高性能 LiDAR 仿真，支持 CPU/Warp/Taichi/Jax 后端、多种传感器类型及 ROS 集成。

## 项目链接

- GitHub: <https://github.com/discoverse-dev/MuJoCo-LiDAR>

## 项目概述

## 项目介绍
MuJoCo-LiDAR是一款基于MuJoCo的高性能激光雷达仿真工具，支持CPU、Taichi、JAX、Warp多种后端，可实现多种激光雷达模型仿真并兼容ROS1/ROS2集成，适用于机器人SLAM、强化学习（RL）等相关仿真研发场景。

## 主要特性
1.  **多后端支持**：包含原生CPU后端（无需GPU）、Taichi GPU并行后端、JAX MJX集成批量仿真后端、Warp NVIDIA光线投射后端（支持动态网格与批量场景）
2.  **高性能**：GPU端可实现每秒100万+光线投射，支持实时BVH构建
3.  **多雷达支持**：内置Velodyne、Livox、Ouster等多款商用雷达模型，同时支持自定义激光扫描模式
4.  **ROS集成**：提供开箱即用的ROS1/ROS2示例代码
5.  支持通过PyPI快速安装，也可从源码编译部署，附带丰富的示例与使用文档。
