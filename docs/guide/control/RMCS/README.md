# RMCS

基于ROS2的RoboMaster控制系统

## 项目链接

- GitHub: <https://github.com/Alliance-Algorithm/RMCS>

## 项目概述

## 项目介绍
RMCS是一款基于ROS2的RoboMaster机器人控制系统，用于RoboMaster机甲大师机器人的开发、部署与运行。项目提供了完整的开发容器化环境与部署方案，支持在Linux/WSL2环境下进行开发，适配x86-64架构，可完成机器人控制代码的编写、构建、运行以及下位机通信调试。

## 主要特性
1.  基于Docker+VSCode Dev Containers提供标准化开发环境，无需手动配置ROS2等依赖
2.  支持原生编译与arm64、amd64架构交叉编译
3.  提供一键构建、运行脚本，简化开发流程
4.  配套下位机通信驱动，支持USB设备接入与权限配置
5.  提供部署镜像，可快速在机器人MiniPC上完成部署运行
