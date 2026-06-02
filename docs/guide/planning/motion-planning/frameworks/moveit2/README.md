# MoveIt 2

MoveIt 2 是 MoveIt! 的 ROS 2 版本，针对现代机器人系统进行了全面优化，支持实时控制、多机器人协作和更灵活的架构设计。

## 简介

MoveIt 2 是 ROS 2 生态中最成熟的运动规划框架，继承了 MoveIt! 的所有核心功能，并针对 ROS 2 的新特性进行了深度优化。

## 核心特性

### ROS 2 原生支持
- 完全基于 ROS 2 中间件
- 支持 DDS 通信机制
- 实时性能优化
- 更好的多进程支持

### 架构改进
- 模块化设计，组件化架构
- 支持动态加载插件
- 改进的动作服务器
- 更好的错误处理

### 新功能
- 多机器人协作规划
- 实时运动规划
- 改进的碰撞检测
- 支持更多运动学求解器

## 项目链接

- 官方网站: https://moveit.ros.org/
- GitHub 仓库: https://github.com/ros-planning/moveit2
- 官方文档: https://moveit.picknik.ai/

## 与 MoveIt! 的对比

| 特性 | MoveIt! (ROS 1) | MoveIt 2 (ROS 2) |
|------|----------------|-----------------|
| 实时控制 | 有限支持 | 原生支持 |
| 多机器人 | 需要额外配置 | 原生支持 |
| 组件化 | 基础支持 | 深度支持 |
| 长期维护 | 逐步停止 | 活跃开发 |

## 应用场景

- 工业机器人操作
- 协作机器人应用
- 多机器人系统
- 研究与教育

## 快速开始

```bash
# 安装 MoveIt 2
sudo apt install ros-humble-moveit

# 运行演示
ros2 launch moveit2_tutorials demo.launch.py
```
