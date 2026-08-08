# Isaac Lab

## 资源简介

Isaac Lab 是 NVIDIA 开发的统一模块化机器人学习框架，旨在简化机器人研究中的常见工作流程。官方定义为"一个统一且模块化的机器人学习框架，旨在简化机器人研究中的常见工作流程（如强化学习、从演示学习和运动规划）"。它基于 NVIDIA Isaac Sim 构建，利用最新的仿真能力提供逼真的场景和高效仿真。

## 官方链接

* 官方文档：<https://isaac-sim.github.io/IsaacLab/main/index.html>
* GitHub仓库：<https://github.com/NVIDIA/IsaacLab>
* 技术报告：<https://arxiv.org/abs/2511.04831>

## 核心设计原则

* **模块化（Modularity）**：轻松定制和添加新环境、机器人和传感器
* **敏捷性（Agility）**：适应社区不断变化的需求
* **开放性（Openness）**：保持开源，允许社区贡献和扩展
* **开箱即用（Batteries-included）**：包含大量可直接使用的环境、传感器和任务

## 核心功能

* **PhysX 物理仿真**：快速准确的物理模拟
* **平铺渲染 API**：用于矢量化渲染
* **域随机化**：提高鲁棒性和适应性
* **云端支持**：支持在云端运行
* **多 GPU/多节点训练**：支持分布式训练

## 支持的机器人平台

* **经典控制**：Cartpole、Humanoid、Ant
* **固定臂和灵巧手**：UR10、Franka、Allegro、Shadow Hand
* **四足机器人**：ANYmal-B/C/D、Unitree A1、Unitree Go1、Unitree Go2、Boston Dynamics Spot
* **人形机器人**：Unitree H1、Unitree G1
* **四旋翼**：Crazyflie

## 核心任务类型

* 经典控制任务
* 固定臂操作任务
* 灵巧手操作任务
* 四足运动控制任务
* 人形机器人任务
* 导航任务

## 支持的学习方法

* 强化学习（PPO、SAC、TD3 等）
* 模仿学习（行为克隆、DAP 等）
* 遥操作与示教学习
* 运动规划（RRT、PRM 等）
