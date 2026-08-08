# ORB-SLAM3-ROS2-Docker

该仓库包含运行 ROS2 Humble 下 Ubuntu 22.04 的 Docker 容器所需的完整内容，以支持 ORB-SLAM3。

## 项目链接

- GitHub: <https://github.com/suchetanrs/ORB-SLAM3-ROS2-Docker>

## 项目概述

## 项目介绍
本项目提供了基于ROS2 Humble（Ubuntu 22.04）的ORB-SLAM3容器化封装，可通过Docker快速部署运行ORB-SLAM3，无需手动配置复杂的编译和依赖环境。推荐使用1.0.0版本以获取稳定版本，master分支为最新特性但未经过充分测试。

## 主要特性
1.  支持标准CPU版本和NVIDIA CUDA加速版本两种Docker镜像构建
2.  内置完整的ORB-SLAM3 ROS2封装，支持单目、单目+IMU、双目、双目+IMU、RGBD、RGBD+IMU多种SLAM配置
3.  提供一键式Docker环境搭建脚本，包含X11转发配置，可可视化运行演示
4.  内置自动构建流程，包含CI构建状态校验
5.  支持通过Euroc数据集或Gazebo仿真进行功能测试
