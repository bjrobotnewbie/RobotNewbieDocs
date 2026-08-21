# Pontryagin-Differentiable-Programming

能够学习控制系统的（神经）控制目标函数、动力学方程、控制策略或最优轨迹的统一端到端学习与控制框架。

## 项目链接

- GitHub: <https://github.com/wanxinjin/Pontryagin-Differentiable-Programming>
- 项目主页: <https://wanxinjin.github.io/Pontryagin-Differentiable-Programming/>

## 项目概述

## 项目介绍
Pontryagin-Differentiable-Programming（PDP）是一个端到端统一学习与控制框架，可用于在控制系统中学习神经控制目标函数、动力学方程、控制策略或最优轨迹。
该项目包含PDP核心包与JinEnv环境包，配套有NeurIPS 2020、IEEE T-RO、NeurIPS 2021相关论文，分别对应基础PDP、连续PDP以及安全PDP变体，还提供了仿真机器人演示博客。

## 主要特性
1.  提供四个独立可复用的核心类：
    - OCSys：用于符号化定义参数化最优控制系统，内置最优控制求解器，可基于庞特里亚金原理求导并获取辅助控制系统
    - LQR：用于定义时变/时不变LQR系统并求解
    - ControlPlanning：支持带参数化策略（多项式或神经网络）的最优控制系统定义与轨迹生成
    - SysID：用于定义参数化动力学方程并进行系统辨识
2.  JinEnv包提供从单倒立摆到6自由度火箭着陆等多种物理系统环境与可视化工具
3.  代码注释详细，易用性强。
