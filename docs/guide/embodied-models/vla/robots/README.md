# robots

通过 Strands Agents 使用自然语言控制机器人和物理硬件。

## 项目链接

- GitHub: <https://github.com/strands-labs/robots>
- 项目主页: <https://strands-labs.github.io/robots/>

## 项目概述

## 项目介绍
Strands Robots是一款基于Strands Agents的机器人控制库，支持通过自然语言控制实体机器人与硬件设备，同时兼容MuJoCo仿真环境。用户可以使用同一套代码，既可以运行MuJoCo仿真（无需GPU与实体硬件），也可以连接真实机器人，还可选择开启点对点mesh网络实现分布式协作。该库支持ROS 2，可完成机器人示教、数据集录制、策略训练、仿真与实体部署全流程。

## 主要特性
1.  统一控制接口：同一套代码即可操控仿真机器人与实体硬件
2.  全流程机器人开发：支持示教录制、LeRobotDataset数据集生成、策略训练、仿真与实体部署
3.  兼容多生态：支持MuJoCo、NVIDIA GR00T、Hugging Face LeRobot等主流机器人开发工具链
4.  支持分布式协作：可通过mesh网络实现机器人 fleet  peer-to-peer协作
5.  自然语言控制：通过Strands Agent直接使用自然语言下发机器人控制指令
