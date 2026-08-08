# walk-these-ways-go2

在Unitree Go2上部署walk-these-ways项目

## 项目链接

- GitHub: <https://github.com/Teddy-Liao/walk-these-ways-go2>

## 项目概述

## 项目介绍
本项目是从`walk-these-ways`复刻的Sim-to-Real四足机器人运动项目，适配宇树Go2机器人。原项目是Go1的Sim-to-Real运动入门套件，可通过简单修改适配A1机器人，本项目针对宇树新版SDK2不再基于UDP的特性，修改了SDK接口，实现将训练好的RL运动策略部署到Unitree Go2上。

## 主要特性
1.  **核心功能**：基于RL训练四足机器人步态策略，支持仿真训练与真实机器人部署
2.  **适配硬件**：专为Unitree Go2优化，适配新版unitree-sdk2
3.  **训练环境**：依赖Isaac Gym、PyTorch1.10+CUDA11.3，需8GB以上显存GPU
4.  **快速上手**：提供预训练模型，可直接运行测试，支持自定义修改机器人与环境参数
5.  **部署支持**：当前支持PC端部署，计划支持Jetson Orin；依赖LCM通信框架与Unitree SDK2实现真实机器人控制
6.  **训练工具**：内置`go2_gym`和`go2_gym_learn`作为训练核心目录，提供训练与模型测试脚本
