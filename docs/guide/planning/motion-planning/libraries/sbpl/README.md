# SBPL (Search-Based Planning Library)

SBPL 是一个基于搜索的运动规划库，专注于离散状态空间的最优规划。它实现了多种启发式搜索算法，支持 anytime 规划和增量修复，广泛应用于移动机器人导航和机械臂运动规划。

## 简介

SBPL（Search-Based Planning Library）是一个开源的 C++ 规划库，专门用于基于搜索的运动规划。它提供了多种启发式搜索算法的实现，支持在高维状态空间中寻找最优路径。

## 核心特性

### 最优性保证
- 支持带权重的 A* 算法
- 提供有界次优解保证
- 支持 anytime 规划

### 增量规划
- 支持环境动态更新
- 增量路径修复
- 高效重新规划

### 多领域支持
- 移动机器人导航
- 机械臂运动规划
- 多机器人协调

## 主要算法

### 基础搜索算法
- **A*** - 经典 A 星算法
- **加权 A*** - 带权重的 A 星，支持速度/质量权衡

### Anytime 算法
- **ARA*** - 任意时间 A 星，逐步改进解的质量
- **ANA*** - 任意时间非参数 A 星，自适应权重调整
- **R*** - 增量路径修复算法，支持环境动态变化

### 多分辨率规划
- **Multi-resolution A*** - 多分辨率搜索，提高效率

## 项目链接

- GitHub 仓库: https://github.com/sbpl/sbpl
- ROS Wiki: https://wiki.ros.org/sbpl
- 参考文档: https://github.com/sbpl/sbpl/wiki

## 与 Navigation Stack 集成

SBPL 是 ROS Navigation Stack 的重要组件，通过 `sbpl_lattice_planner` 提供：

- 全局路径规划
- 动力学约束考虑
- 最优路径保证
- 支持自定义运动原语

## 运动原语 (Motion Primitives)

SBPL 的核心概念是运动原语，预定义一组离散的运动：

```
移动机器人典型原语：
- 前进
- 左转
- 右转
- 原地旋转
- 斜向移动
```

## 应用场景

- 移动机器人自主导航
- AGV/AMR 路径规划
- 机械臂运动规划
- 多机器人路径规划
- 研究与教育

## 核心概念

### 启发函数 (Heuristic)
- 估计从当前状态到目标的代价
- 可采纳性保证最优性
- 一致性保证搜索效率

### 状态格 (State Lattice)
- 离散化连续状态空间
- 预定义运动原语连接
- 支持动力学约束

### 环境表示
- 栅格地图
- 成本地图
- 碰撞检测

## 快速开始

```cpp
#include <sbpl/headers.h>

// 创建环境
EnvironmentNAVXYTHETALAT env;
env.InitializeEnv(width, height, mapdata, startx, starty, starttheta,
                  goalx, goaly, goaltheta,
                  nominalvel_mpersecs, timetoturn45degsinplace_secs,
                  obsthresh, cellsize_m);

// 创建规划器
ARAPlanner planner(&env, true);

// 设置规划参数
planner.set_start(start_state_id);
planner.set_goal(goal_state_id);

// 执行规划
std::vector<int> solution_stateIDs;
int cost;
planner.replan(10.0, &solution_stateIDs, &cost);

// 提取路径
env.ConvertStateIDPathintoXYThetaPath(&solution_stateIDs, &path);
```

## 算法对比

| 算法 | 最优性 | Anytime | 增量 | 典型应用 |
|------|--------|---------|------|---------|
| A* | ✅ 最优 | ❌ | ❌ | 静态环境 |
| ARA* | ⚠️ 有界 | ✅ | ❌ | 时间受限场景 |
| ANA* | ⚠️ 有界 | ✅ | ❌ | 自适应场景 |
| R* | ⚠️ 有界 | ✅ | ✅ | 动态环境 |
