# OpenKAI

OpenKAI：一个用于无人载具与机器人控制的现代框架

## 项目链接

- GitHub: <https://github.com/yankailab/OpenKAI>

## 项目概述

## 项目介绍
OpenKAI是一款开源的无人车与机器人控制轻量化并行框架，用于快速原型开发与项目搭建。它采用纯C++编写的模块化多线程架构，可在嵌入式硬件上轻量运行，同时也能适配高性能平台扩展资源，支持自定义修改与新设备扩展，已适配x86 PC、NVIDIA Jetson系列、Raspberry Pi等平台。

## 主要特性
1.  **核心能力**：支持无人车/机器人快速开发，统一模块化架构，轻量可扩展
2.  **依赖与接口**：基础依赖Pthread、glog、Eigen，可选支持OpenCV、Open3D等；支持UART、USB、CAN、RS-485、以太网等多种硬件接口
3.  **协议与外设**：内置Mavlink 2、Modbus、TCP/UDP等通信协议，兼容Mavlink飞控、东方电机等外部控制器，支持Intel Realsense、Livox等多款传感器
4.  支持多类主流嵌入式与桌面开发平台，社区与厂商可共同贡献设备支持代码。
