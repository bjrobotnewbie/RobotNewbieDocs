# 运动规划 (Motion Planning)

运动规划是机器人学的核心分支之一，研究如何为机器人生成无碰撞、满足运动学和动力学约束的运动轨迹。与路径规划不同，运动规划关注的是**如何运动**，而不仅仅是**走哪条路**。

## 分类总览

| 分类 | 定位 | 核心内容 | 典型代表 |
|------|------|---------|---------|
| [**集成框架**](planning/motion-planning/frameworks/README.md) | 完整解决方案 | 运动学求解、碰撞检测、可视化 | MoveIt!, MoveIt 2 |
| [**算法库**](planning/motion-planning/libraries/README.md) | 底层算法实现 | 规划算法核心实现 | OMPL, SBPL |
| [**轨迹优化**](planning/motion-planning/optimization/README.md) | 轨迹质量提升 | 数值优化、平滑约束 | CHOMP, STOMP |

---

## 核心概念

### 构型空间 (Configuration Space, C-Space)

机器人所有可能的关节角度组合构成的空间。运动规划的本质是在 C-Space 中找到一条从起始构型到目标构型的无碰撞路径。

### 轨迹 vs 路径

| 概念 | 包含信息 | 输出 |
|------|---------|------|
| **路径 (Path)** | 几何位置序列 | [q0, q1, q2, ..., qn] |
| **轨迹 (Trajectory)** | 位置 + 速度 + 加速度 + 时间 | [q(t), q̇(t), q̈(t)] |

### 约束类型

- **运动学约束**：关节限制、速度限制、加速度限制
- **动力学约束**：力矩限制、惯性约束
- **避障约束**：与障碍物保持安全距离
- **任务约束**：末端执行器姿态、操作约束

---

## 规划器分类

### 基于采样的规划器 (OMPL)

通过随机采样探索状态空间，概率完备但不保证最优。

**典型算法：** RRT, RRT*, PRM, EST, KPIECE

**特点：**
- 适合高维空间
- 计算效率高
- 路径质量可能不稳定

### 基于搜索的规划器 (SBPL)

将状态空间离散化，使用图搜索算法寻找最优路径。

**典型算法：** A*, ARA*, ANA*, R*

**特点：**
- 有界次优性保证
- 支持增量重规划
- 随维度增长复杂度指数上升

### 轨迹优化方法 (CHOMP, STOMP)

将规划转化为数值优化问题，最小化代价函数。

**典型算法：** CHOMP, STOMP

**特点：**
- 生成平滑轨迹
- 支持多种约束
- 可能陷入局部最优

---

## 与路径规划的区别

| 特性 | 路径规划 (Path Planning) | 运动规划 (Motion Planning) |
|------|-------------------------|---------------------------|
| **输出** | 几何路径点 | 带时间参数的轨迹 |
| **约束** | 仅避障 | 运动学、动力学、速度、加速度 |
| **空间维度** | 2D/3D 任务空间 | 关节空间（通常 6-7 维） |
| **典型算法** | A*, RRT*, Dijkstra | CHOMP, STOMP, IK |
| **应用对象** | 移动机器人 | 机械臂、人形机器人 |

---

## 技术选型指南

| 应用场景 | 推荐方案 |
|---------|---------|
| 机械臂拾取放置 | MoveIt! + OMPL + CHOMP |
| 移动机器人导航 | SBPL + DWA |
| 复杂环境作业 | MoveIt! + STOMP |
| 研究新算法 | OMPL（扩展开发） |
| ROS 2 新项目 | MoveIt 2 |

---

## 详细文档

### [集成框架](planning/motion-planning/frameworks/README.md)
- [MoveIt!](planning/motion-planning/frameworks/moveit/README.md) - ROS 1 运动规划标准框架
- [MoveIt 2](planning/motion-planning/frameworks/moveit2/README.md) - ROS 2 下一代框架

### [算法库](planning/motion-planning/libraries/README.md)
- [OMPL](planning/motion-planning/libraries/ompl/README.md) - 开源运动规划库
- [SBPL](planning/motion-planning/libraries/sbpl/README.md) - 基于搜索的规划库

### [轨迹优化](planning/motion-planning/optimization/README.md)
- [CHOMP](planning/motion-planning/optimization/chomp/README.md) - 协变哈密顿优化
- [STOMP](planning/motion-planning/optimization/stomp/README.md) - 随机轨迹优化

---

## 典型工作流

```
1. 问题定义
   ├─ 起始构型
   ├─ 目标约束
   └─ 环境模型

2. 规划器选择
   ├─ 基于采样？
   ├─ 基于搜索？
   └─ 轨迹优化？

3. 规划求解
   ├─ 调用规划器
   ├─ 检查可行性
   └─ 优化（可选）

4. 后处理
   ├─ 时间参数化
   ├─ 轨迹平滑
   └─ 碰撞复检

5. 执行控制
   └─ 发送轨迹给控制器
```

---

## 相关资源

- [MoveIt! 官方文档](https://moveit.ros.org/)
- [OMPL 官方文档](https://ompl.kavrakilab.org/)
- [SBPL 官方文档](https://sbpl.net/)
- [机器人运动规划教材](http://motion.cs.illinois.edu/RoboticSystemsBook/)
