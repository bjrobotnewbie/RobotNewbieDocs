# elodin

Elodin 是包含仿真、飞行软件和可视化工具的单仓库项目，面向飞行器软件栈开发。

## 项目链接

- GitHub: <https://github.com/elodin-sys/elodin>
- 项目主页: https://docs.elodin.systems

## 项目概述

Elodin monorepo 集成了飞行软件、仿真软件和开发工具。飞行软件部分包含 Aleph NixOS 模块、时序数据库与消息总线、串口传感器桥、姿态估计 MEKF、传感器固件等组件；仿真部分提供 nox-py Python SDK，并支持 ECS 与 JAX 集成；编辑器则用于 3D 可视化和飞行/仿真数据图表展示。

项目定位更接近航天/飞行器软件基础设施，而不是单一仿真器。它适合需要统一管理飞控软件、遥测、传感器数据、仿真和可视化的团队，尤其适合围绕 Orin 等边缘计算硬件构建可复现开发环境和仿真-飞行闭环工具链。
