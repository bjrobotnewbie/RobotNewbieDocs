# unitree_ros2

## 项目链接

- GitHub: <https://github.com/unitreerobotics/unitree_ros2>

## 项目概述

## 项目介绍
本项目是Unitree机器人的ROS2支持包，基于Cyclonedds实现，可直接通过ROS2消息完成对Unitree Go2、B2、H1三款机器人的通信与控制，无需额外封装SDK接口。项目兼容基于Cyclonedds的Unitree SDK2通信机制，适配ROS2的DDS通信底层架构。

## 主要特性
1.  **支持机型**：Unitree Go2、B2、H1机器人
2.  **通信方式**：直接使用ROS2消息完成机器人控制与通信，无需二次封装SDK
3.  **系统适配**：测试适配Ubuntu20.04+ROS2 Foxy、Ubuntu22.04+ROS2 Humble（推荐）
4.  **开发环境**：提供Docker、VSCode Dev Container、Github Codespaces快速搭建方式，附带编译脚本辅助排障

## 快速安装说明
以ROS2 Foxy为例，需先安装对应依赖，克隆仓库后可选择编译CycloneDDS（Humble版本可跳过），完成包编译即可使用。
