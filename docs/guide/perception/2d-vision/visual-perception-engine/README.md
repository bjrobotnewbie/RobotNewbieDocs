# visual-perception-engine

视觉感知引擎：一款旨在NVIDIA Jetson上以优化并发方式运行多个感知模型的快速灵活框架

## 项目链接

- GitHub: <https://github.com/nasa-jpl/visual-perception-engine>

## 项目概述

## 项目介绍
Visual Perception Engine是一款面向机器人视觉任务的快速灵活框架，专为NVIDIA Jetson平台优化，支持以并发高效的方式运行多感知模型。该项目由NASA JPL开发，可统一处理视觉输入，输出单目深度、语义分割、目标检测等感知结果，支持实时运行（≥50Hz）。框架内置基于DepthAnythingV2的单目深度估计、语义分割以及纯PyTorch实现的目标检测，同时提供C++ ROS 2（Humble）节点，可快速集成到现有机器人栈中。

## 主要特性
1.  **高效灵活**：基于DINOv2视觉基础模型提取通用特征，搭配多个模型头完成不同感知任务，支持TensorRT和PyTorch两种模型格式，各模块以独立进程运行，通过自定义GPU张量队列传输数据
2.  **可扩展易配置**：支持自定义添加模型头或修改现有模块，运行时可灵活控制
3.  **适配机器人场景**：提供ROS 2节点，支持在Jetson Orin AGX（Jetpack 6.1+）设备上部署运行
4.  **高性能**：可实现≥50Hz的实时感知推理
