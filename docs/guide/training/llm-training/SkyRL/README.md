# SkyRL

SkyRL: 面向大语言模型（LLMs）的模块化全栈RL库

## 项目链接

- GitHub: <https://github.com/NovaSky-AI/SkyRL>
- 项目主页: https://docs.skyrl.ai/docs

## 项目概述

## 项目介绍
SkyRL是一款模块化全栈大语言模型强化学习（RL）库，提供完整的RL开发栈。项目包含四个核心子模块：`skyrl`统一本地硬件RL训练库，整合了高性能训练框架`skyrl-train`与支持Tinker API的跨平台后端库`skyrl-tx`；`skyrl-agent`用于长时序、真实场景智能体训练；`skyrl-gym`提供基于Gymnasium API的工具使用任务环境库，涵盖数学、编码、搜索、SQL等场景。

## 主要特性
1.  全栈式RL开发支持，覆盖训练、环境搭建、智能体流水线全流程
2.  支持Tinker API，可在本地GPU运行Tinker API训练脚本
3.  模块化设计，可灵活扩展、修改或基于项目构建自定义RL训练栈
4.  内置多类型工具使用任务环境，适配多场景智能体训练
5.  支持多种大语言模型，适配真实长时序、多轮工具使用任务
