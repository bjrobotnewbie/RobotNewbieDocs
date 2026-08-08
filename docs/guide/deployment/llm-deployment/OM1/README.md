# OM1

面向机器人的模块化AI HAL（硬件抽象层）

## 项目链接

- GitHub: <https://github.com/OpenMind/OM1>
- 项目主页: <https://openmind.com>

## 项目概述

## 项目介绍
OM1是OpenMind推出的模块化AI硬件抽象层(HAL)，同时也是多模态AI运行时，支持开发者在数字环境和实体机器人（包括人形机器人、 quadruped机器人、TurtleBot 4等教育机器人，以及Gazebo、Isaac Sim等模拟器）上创建和部署AI智能体。
它可以处理网页数据、社交媒体内容、摄像头画面、激光雷达等多源输入，支持运动控制、自主导航、自然对话等物理交互，目标是简化高能力人形机器人的开发，便于升级和适配不同硬件形态。
项目提供Go和Python两种运行时，Go版本性能更优，Python版本已停止维护。

## 主要特性
1.  **模块化架构**：基于Go开发，兼顾性能与集成便捷性
2.  **灵活数据接入**：轻松对接各类数据源与传感器
3.  **硬件插件支持**：通过插件兼容ROS2、Zenoh、CycloneDDS等协议，支持多种机器人硬件
4.  **预置服务端点**：内置多厂商LLM、本地Ollama以及视觉语言模型(VLM)、文本转语音的预置接口
5.  **可观测性工具**：集成Prometheus和Grafana栈，实时监控AI pipeline的LLM、ASR等延迟指标
