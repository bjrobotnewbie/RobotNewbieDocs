# 运动规划集成框架

运动规划集成框架提供了完整的运动规划解决方案，包括运动学求解、碰撞检测、可视化等全套工具链。这些框架通常与 ROS 生态系统深度集成，是工业机器人和研究平台的首选。

## 框架概览

| 框架 | 支持 ROS 版本 | 主要特性 | 适用场景 |
|------|--------------|---------|---------|
| [**MoveIt!**](planning/motion-planning/frameworks/moveit/README.md) | ROS 1 | 成熟稳定，生态丰富 | 现有 ROS 1 项目 |
| [**MoveIt 2**](planning/motion-planning/frameworks/moveit2/README.md) | ROS 2 | 实时支持，多机协作 | 新项目，ROS 2 生态 |

## 核心功能对比

### MoveIt! (ROS 1)

MoveIt! 是 ROS 1 生态中最成熟的运动规划框架，经过多年的发展和工业验证。

**核心优势：**
- ✅ 成熟稳定，工业验证
- ✅ 丰富的插件生态
- ✅ 完整的文档和教程
- ✅ 大量成功案例

**主要功能：**
- 多规划器支持（OMPL, CHOMP, STOMP）
- 碰撞检测（FCL）
- 运动学求解（IKFast, TRAC-IK）
- RViz 可视化插件
- 拾取放置 Pipeline

---

### MoveIt 2 (ROS 2)

MoveIt 2 是 MoveIt! 的下一代版本，针对 ROS 2 进行了全面优化。

**核心优势：**
- ✅ ROS 2 原生支持
- ✅ 实时运动规划
- ✅ 多机器人协作
- ✅ 组件化架构

**主要改进：**
- 基于 ROS 2 Action 通信
- 改进的插件系统
- 更好的错误处理
- 支持安全关键系统

## 架构对比

| 组件 | MoveIt! | MoveIt 2 |
|------|---------|---------|
| 通信层 | ROS 1 Action | ROS 2 Action |
| 节点模型 | 单节点 | 组件化 |
| 实时性 | 有限支持 | 原生支持 |
| 参数系统 | ROS 1 参数 | ROS 2 参数 |
| 日志系统 | rosconsole | rcutils |

## 选择指南

### 选择 MoveIt! 如果：
- 现有项目基于 ROS 1
- 需要成熟稳定的解决方案
- 依赖特定 ROS 1 生态包
- 不需要实时控制

### 选择 MoveIt 2 如果：
- 新项目从零开始
- 需要实时控制能力
- 多机器人协作场景
- 关注长期维护和支持

## 快速开始

### MoveIt! 安装

```bash
# ROS Noetic
sudo apt install ros-noetic-moveit
```

### MoveIt 2 安装

```bash
# ROS Humble
sudo apt install ros-humble-moveit
```

## 相关资源

- [MoveIt! 官方文档](https://moveit.ros.org/)
- [MoveIt 2 官方文档](https://moveit.picknik.ai/)
- [MoveIt 教程](https://moveit.ros.org/documentation/tutorials/)
