# 运动规划 (Motion Planning)

运动规划是机器人学的核心分支之一，研究如何为机器人生成无碰撞、满足运动学和动力学约束的运动轨迹。与路径规划不同，运动规划关注的是**如何运动**，而不仅仅是**走哪条路**。

## 分类总览

| 分类 | 定位 | 主要内容 | 典型代表 |
|------|------|---------|---------|
| [**集成框架**](/guide/planning/motion-planning/frameworks/README) | 完整解决方案 | 运动学求解、碰撞检测、可视化 | MoveIt!, MoveIt 2 |
| [**算法库**](/guide/planning/motion-planning/libraries/README) | 底层算法实现 | 规划算法核心实现 | OMPL, SBPL |
| [**轨迹优化**](/guide/planning/motion-planning/optimization/README) | 轨迹质量提升 | 数值优化、平滑约束 | CHOMP, STOMP |

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

### [集成框架](/guide/planning/motion-planning/frameworks/README)
- [MoveIt!](/guide/planning/motion-planning/frameworks/moveit/README) - ROS 1 运动规划标准框架
- [MoveIt 2](/guide/planning/motion-planning/frameworks/moveit2/README) - ROS 2 下一代框架

### [算法库](/guide/planning/motion-planning/libraries/README)
- [OMPL](/guide/planning/motion-planning/libraries/ompl/README) - 开源运动规划库
- [SBPL](/guide/planning/motion-planning/libraries/sbpl/README) - 基于搜索的规划库

### [轨迹优化](/guide/planning/motion-planning/optimization/README)
- [CHOMP](/guide/planning/motion-planning/optimization/chomp/README) - 协变哈密顿优化
- [STOMP](/guide/planning/motion-planning/optimization/stomp/README) - 随机轨迹优化

### 运动规划库与工具

- [curobo](/guide/planning/curobo/README) - NVIDIA CUDA 加速机器人运动生成库，支持 IK、碰撞检测、轨迹优化
- [MPlib](/guide/planning/MPlib/README) - 轻量级 Python 运动规划库，脱离 ROS 依赖
- [openrave](/guide/planning/openrave/README) - 经典机器人运动规划仿真环境
- [tesseract](/guide/planning/tesseract/README) - 运动规划环境框架，支持 IK、碰撞检测和轨迹规划
- [pyroboplan](/guide/planning/pyroboplan/README) - 面向教育的 Python 机械臂运动规划库
- [roboplan](/guide/planning/roboplan/README) - 基于 Pinocchio 的现代机器人运动规划库
- [python_motion_planning](/guide/planning/python_motion_planning/README) - 运动规划算法 Python 实现集合，含可视化
- [dynoplan](/guide/planning/dynoplan/README) - 动力学约束运动规划库，含 RRT*-TO、SST*、iDb-A* 算法
- [ruckig](/guide/planning/ruckig/README) - 即时在线轨迹生成库，支持 jerk 约束
- [toppra](/guide/planning/toppra/README) - 时间最优路径参数化（TOPP-RA）运动规划库
- [cuTAMP](/guide/planning/cuTAMP/README) - GPU 并行任务与运动规划（TAMP）框架
- [HRVO](/guide/planning/HRVO/README) - 混合互惠速度障碍（HRVO）C++ 库，用于多智能体避碰
- [RVO2](/guide/planning/RVO2/README) - ORCA 最优互惠碰撞避免算法 C++ 实现
- [RVO2-3D](/guide/planning/RVO2-3D/README) - ORCA 算法的三维空间实现
- [RVO2-CS](/guide/planning/RVO2-CS/README) - ORCA 算法的 C# 实现版本
- [SCAN-Planner](/guide/planning/SCAN-Planner/README) - 四足机器人空间碰撞感知局部规划器

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

- [ompl（开放运动规划库（OMPL））](/guide/planning/motion-planning/ompl/README)

- [routingpy（🌎 这是一个 Python 库，用于以统…）](/guide/planning/motion-planning/routingpy/README)

- [vamp（SIMD加速的基于采样的运动规划）](/guide/planning/motion-planning/vamp/README)

- [isaac_ros_cumotion（用于机械臂运动规划与控制的NVIDIA加…）](/guide/planning/motion-planning/isaac_ros_cumotion/README)

- [moveit2（：机器人：MoveIt for ROS …）](/guide/planning/motion-planning/moveit2/README)

- [moveit（:robot: MoveIt 运动规划框…）](/guide/planning/motion-planning/moveit/README)

- [RDA-planner（[RA-Letter 2023] RDA…）](/guide/planning/motion-planning/RDA-planner/README)

- [mighty（MIGHTY：一种基于 Hermite …）](/guide/planning/motion-planning/mighty/README)

- [lacam3（LaCAM*：面向实时、大规模及近乎最优…）](/guide/planning/motion-planning/lacam3/README)

- [polyanya（基于 Polyanya 的路径规划）](/guide/planning/motion-planning/polyanya/README)

- [frenet（将 Frenet (s,d) 坐标变换为…）](/guide/planning/motion-planning/frenet/README)

- [Heuristic_path_planners（包含类与函数集合，支持基于启发式算法（如…）](/guide/planning/motion-planning/Heuristic_path_planners/README)
