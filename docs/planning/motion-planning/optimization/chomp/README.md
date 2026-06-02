# CHOMP (Covariant Hamiltonian Optimization for Motion Planning)

CHOMP 是一种基于梯度的轨迹优化算法，通过最小化代价函数生成平滑、无碰撞的运动轨迹。它是 MoveIt! 中常用的轨迹优化器之一，特别适用于机械臂运动规划。

## 简介

CHOMP（Covariant Hamiltonian Optimization for Motion Planning）将运动规划转化为数值优化问题，通过协变哈密顿梯度下降法优化轨迹。它能够同时考虑平滑性和避障约束，生成高质量的运动轨迹。

## 核心思想

CHOMP 的核心是将轨迹表示为高维空间中的曲线，通过迭代优化最小化综合代价：

```
总代价 = 平滑代价 + 碰撞代价
```

### 平滑代价
- 衡量轨迹的加速度
- 鼓励平滑的运动
- 基于轨迹的二阶导数

### 碰撞代价
- 衡量与障碍物的距离
- 惩罚穿透障碍物的轨迹点
- 使用有符号距离场（SDF）计算

## 核心特性

### 协变梯度下降
- 自然适应构型空间的几何结构
- 不需要显式的投影步骤
- 收敛速度快

### 多目标优化
- 同时优化平滑性和避障
- 支持权重调整
- 灵活的代价函数设计

### 数值稳定性
- 鲁棒的优化算法
- 支持多种终止条件
- 参数可配置

## 算法流程

```
1. 初始化初始轨迹（通常是直线或粗略路径）
2. 计算当前轨迹的代价函数值
3. 计算协变梯度
4. 执行梯度下降步骤更新轨迹
5. 检查收敛条件
6. 重复步骤 2-5 直到收敛或达到最大迭代次数
```

## 项目链接

- 原始论文: https://www.ri.cmu.edu/pub_files/2009/5/chomp_icra09.pdf
- 参考实现: https://github.com/ros-planning/moveit/tree/main/moveit_planners/chomp

## 与 MoveIt! 集成

CHOMP 在 MoveIt! 中通过 `chomp_planner` 插件提供：

- 作为独立规划器使用
- 作为其他规划器的后处理优化
- 支持多种配置参数

### 主要配置参数

| 参数 | 说明 | 典型值 |
|------|------|--------|
| `planning_time_limit` | 规划时间限制 | 5.0s |
| `max_iterations` | 最大迭代次数 | 200 |
| `collision_threshold` | 碰撞距离阈值 | 0.07m |
| `ridge_factor` | 正则化系数 | 0.001 |
| `learning_rate` | 梯度下降步长 | 0.01 |

## 优势与局限

### 优势
- ✅ 生成高度平滑的轨迹
- ✅ 计算效率高
- ✅ 支持高维空间
- ✅ 数值稳定性好

### 局限
- ❌ 可能陷入局部最优
- ❌ 对初始轨迹敏感
- ❌ 超参数调优复杂
- ❌ 不保证找到可行解

## 应用场景

- 工业机械臂运动
- 协作机器人轨迹生成
- 拾取放置操作
- 需要平滑运动的场景

## CHOMP vs STOMP

| 特性 | CHOMP | STOMP |
|------|--------|-------|
| 优化方法 | 梯度下降 | 随机采样 |
| 局部最优 | 容易陷入 | 更易逃脱 |
| 计算效率 | 高 | 中等 |
| 参数调优 | 复杂 | 简单 |
| 确定性 | ✅ 确定 | ❌ 随机 |

## 快速开始

### MoveIt! 配置

```yaml
chomp_planner:
  planning_time_limit: 5.0
  max_iterations: 200
  collision_threshold: 0.07
  ridge_factor: 0.001
  learning_rate: 0.01
  add_randomness: false
  smoothness_cost_weight: 0.1
  obstacle_cost_weight: 1.0
```

### 使用优化器

```cpp
// 创建 CHOMP 优化器
chomp::CHOMPOptimizer optimizer(robot_model, planning_scene);

// 设置参数
optimizer.setPlanningTimeLimit(5.0);
optimizer.setMaxIterations(200);

// 执行优化
robot_trajectory::RobotTrajectory trajectory(robot_model, group_name);
bool success = optimizer.optimize(start_state, goal_constraints, trajectory);
```

## 调优建议

1. **平滑性 vs 避障**
   - 增加 `smoothness_cost_weight` 获得更平滑的轨迹
   - 增加 `obstacle_cost_weight` 提高避障优先级

2. **收敛速度**
   - 调整 `learning_rate` 控制步长
   - 减小 `max_iterations` 加快返回

3. **鲁棒性**
   - 启用 `add_randomness` 帮助逃脱局部最优
   - 调整 `ridge_factor` 改善数值稳定性
