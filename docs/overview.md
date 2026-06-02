# 知识库概览

欢迎来到**机器小白知识库**！这是一个面向具身智能机器人领域的开源知识平台，旨在为初学者、研究者和开发者提供系统化、实践导向的学习资源。无论你是刚入门的机器人爱好者，还是深耕具身智能的科研人员，都能在这里找到有价值的内容。

## 🗺️ 知识库架构总览

本知识库按照机器人技术栈分层组织，涵盖从基础理论到应用落地的完整知识体系：

| 层级 | 分类名称 | 核心内容 | 学习路径 |
|------|---------|---------|:-------:|
| **基础层** | [数学基础](math/README.md) | 微积分、线性代数、概率论、优化理论 | ⭐ 入门必修 |
| **基础层** | [机器人学原理](robotics/README.md) | 运动学、动力学、控制理论 | ⭐ 核心基础 |
| **工具层** | [机器人操作系统](ros/README.md) | ROS1、ROS2、Drake、PyRobot 等 | 🔧 开发工具 |
| **模型层** | [基础模型](foundation-models/README.md) | VLA、WAM、VLN 三大方向 | 🚀 前沿技术 |
| **感知层** | [感知系统](perception/README.md) | 2D 视觉、3D 视觉、多传感器融合 | 👁️ 环境感知 |
| **决策层** | [决策与规划](planning/README.md) | 路径规划、运动规划、任务规划 | 🧠 智能核心 |
| **导航层** | [导航系统](navigation/README.md) | SLAM、视觉导航 | 🧭 自主移动 |
| **控制层** | [控制系统](control/README.md) | 经典控制、现代控制、鲁棒控制 | 🎮 执行控制 |
| **仿真层** | [仿真与世界模型](simulation/README.md) | MuJoCo、Isaac Sim、Gazebo 等 | 🔬 虚拟验证 |
| **模型层** | [世界模型](world-models/README.md) | 各类世界模型实现 | 🌍 预测学习 |
| **数据层** | [具身数据](data/README.md) | 数据集、数据收集、评测基准 | 💾 数据基础 |
| **训练层** | [训练框架](training/README.md) | Isaac Lab、LeRobot、Habitat Lab 等 | 🎯 模型训练 |
| **部署层** | [模型部署](deployment/README.md) | vLLM、Ollama 等推理框架 | ⚡ 落地部署 |
| **硬件层** | [硬件系统](hardware/README.md) | 传感器、电机控制、嵌入式系统 | 🔩 物理实现 |
| **形态层** | [机器人形态分类](robot-forms/README.md) | 刚性、软体、模块化、群体机器人 | 🤖 形态多样性 |
| **应用层** | [应用场景](applications/README.md) | 人形、工业、医疗、服务、农业、无人机 | 🏭 场景落地 |

## 🛤️ 学习路径推荐

根据不同背景和目标，我们为你设计了三条推荐学习路径：

### 🔰 初学者路径
```
数学基础 → 机器人学原理 → ROS → 仿真环境 → 简单项目
```
适合零基础入门，循序渐进建立机器人系统认知。

### 🔬 研究者路径
```
基础模型 → 世界模型 → 训练框架 → 评测基准 → 前沿论文
```
聚焦具身智能前沿，适合从事科研工作的同学。

### 💻 开发者路径
```
ROS → 仿真环境 → 硬件系统 → 模型部署 → 应用开发
```
注重工程实践，快速上手机器人系统开发。

## 🔥 热点内容推荐

当前最值得关注的项目和方向：

- **VLA 模型** - [OpenVLA](foundation-models/vla/openvla/README.md)、[Octo](foundation-models/vla/octo/README.md)、[GR00T](foundation-models/vla/gr00t/README.md) 等视觉语言动作模型
- **训练框架** - [Isaac Lab](training/isaaclab/README.md)、[LeRobot](training/lerobot/README.md) 等机器人训练平台
- **世界模型** - 各类动力学预测模型，探索世界如何运作
- **具身数据集** - [Open X-Embodiment](data/datasets/open-x-embodiment/README.md)、[RH20T](data/datasets/rh20t/README.md) 等大规模数据集
- **仿真引擎** - [MuJoCo](simulation/mujoco/README.md)、[Isaac Sim](simulation/isaacsim/README.md) 高性能物理仿真

## ✨ 知识库特色

- 📚 **体系完整** - 从数学基础到应用场景，构建完整的机器人知识图谱
- 🚀 **紧跟前沿** - 持续更新最新论文和开源项目，把握技术发展脉搏
- 🛠️ **实践导向** - 注重代码实现和工程落地，提供可运行的示例代码
- 🌐 **开源开放** - 所有内容开源免费，欢迎社区共同贡献维护

## 💡 使用指南

- **浏览导航** - 通过左侧边栏按分类浏览，层级清晰便于定位
- **全文搜索** - 使用右上角搜索功能，快速找到感兴趣的内容
- **参与贡献** - 点击页面底部"在 GitHub 上编辑此页"，欢迎提交 PR 完善内容

---

## ❓ 快速开始

> **Q: 我是零基础，应该从哪里开始？**
> 
> 建议先从 [数学基础](math/README.md) 和 [机器人学原理](robotics/README.md) 建立理论基础，然后配合 [ROS](ros/README.md) 教程动手实践。[初学者路径](other/embodied-ai-start/README.md) 章节有更详细的学习指南。

> **Q: 我想做具身智能研究，重点看哪些内容？**
> 
> 重点关注 [基础模型](foundation-models/README.md) 中的 VLA 和 WAM 方向，以及 [训练框架](training/README.md) 和 [世界模型](world-models/README.md) 章节。[具身数据](data/README.md) 部分提供了丰富的评测基准。

> **Q: 如何在本地运行这些项目？**
> 
> 每个项目的 README 都有详细的环境配置和运行说明。建议先从 [仿真环境](simulation/README.md) 开始，在 MuJoCo 或 Isaac Sim 中验证算法后再考虑硬件部署。

> **Q: 如何参与贡献？**
> 
> 发现错误或有更好的内容，直接点击页面底部的编辑链接提交 PR。我们欢迎任何形式的贡献！

---

🌟 开始你的机器人学习之旅吧！左侧是完整的知识目录，祝你探索愉快！
