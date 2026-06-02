# STOMP (Stochastic Trajectory Optimization for Motion Planning)

STOMP 是一种基于随机采样的轨迹优化算法，通过概率采样方法探索轨迹空间，能够有效逃脱局部最优解。它是 MoveIt! 中常用的轨迹优化器，特别适用于复杂环境下的运动规划。

## 简介

STOMP（Stochastic Trajectory Optimization for Motion Planning）结合了基于采样和基于梯度的优化方法的优点，通过在轨迹周围采样噪声轨迹来估计梯度，从而优化轨迹。这种方法能够在高维空间中找到高质量的解，同时对局部最优具有较好的鲁棒性。

## 核心思想

STOMP 的核心是通过随机采样来探索轨迹空间，而不是计算显式梯度：

```
1. 在当前轨迹周围采样多条带噪声的轨迹
2. 评估每条采样轨迹的代价（平滑性 + 碰撞）
3. 根据代价计算每条轨迹的权重
4. 使用权重更新轨迹参数向低代价方向收敛
```

## 核心特性

### 随机采样优化
- 不需要显式计算梯度
- 能够逃脱局部最优
- 鲁棒性强

### 无碰撞约束
- 支持硬约束和软约束
- 灵活的碰撞代价模型
- 支持距离场和深度传感器

### 多目标优化
- 平滑性、避障、关节限制
- 可配置的权重系统
- 支持自定义代价函数

## 算法流程

```
1. 初始化初始轨迹（线性插值或其他方法）
2. 循环直到收敛或达到最大迭代：
   a. 在当前轨迹周围采样 N 条带噪声的轨迹
   b. 计算每条采样轨迹的总代价
   c. 根据代价计算轨迹的概率权重
   d. 使用加权平均更新控制量参数
   e. 应用控制量更新轨迹
   f. 检查收敛条件
3. 返回优化后的轨迹
```

## 项目链接

- 原始论文: https://www.ri.cmu.edu/pub_files/2011/5/stomp_icra11.pdf
- 参考实现: https://github.com/ros-planning/moveit/tree/main/moveit_planners/stomp

## 与 MoveIt! 集成

STOMP 在 MoveIt! 中通过 `stomp_planner` 插件提供：

- 作为独立规划器使用
- 与 OMPL 等规划器结合使用
- 支持多种配置参数和代价函数

### 主要配置参数

| 参数 | 说明 | 典型值 |
|------|------|--------|
| `planning_time_limit` | 规划时间限制 | 5.0s |
| `max_iterations` | 最大迭代次数 | 50 |
| `num_timesteps` | 轨迹时间步数 | 30 |
| `num_rollouts` | 每次迭代采样数 | 30 |
| `noise_stddev` | 采样噪声标准差 | 1.0 |
| `cost_weight` | 碰撞代价权重 | 0.025 |

## 优势与局限

### 优势
- ✅ 对局部最优鲁棒性好
- ✅ 不需要梯度计算
- ✅ 参数调优相对简单
- ✅ 支持高维空间
- ✅ 容易并行化

### 局限
- ❌ 结果具有随机性
- ❌ 收敛速度较慢
- ❌ 计算量较大
- ❌ 需要更多采样

## 应用场景

- 复杂环境下的机械臂运动
- 存在多个局部最优的场景
- 需要高鲁棒性的应用
- 工业机器人操作

## STOMP vs CHOMP

| 特性 | STOMP | CHOMP |
|------|--------|-------|
| 优化方法 | 随机采样 | 梯度下降 |
| 局部最优 | 更易逃脱 | 容易陷入 |
| 计算效率 | 中等 | 高 |
| 参数调优 | 简单 | 复杂 |
| 确定性 | ❌ 随机 | ✅ 确定 |
| 梯度计算 | ❌ 不需要 | ✅ 需要 |
| 并行化 | ✅ 容易 | ⚠️ 困难 |

## 核心概念

### 轨迹参数化
STOMP 使用控制量参数化轨迹，通常是加速度：

```
位置 ← 速度 ← 加速度（控制量）
```

### 噪声采样
- 在控制量空间添加高斯噪声
- 生成多条探索轨迹
- 探索可能的改进方向

### 代价加权
- 低代价轨迹权重高
- 高代价轨迹权重低
- 概率分布引导优化方向

## 快速开始

### MoveIt! 配置

```yaml
stomp_planner:
  planning_time_limit: 5.0
  max_iterations: 50
  num_timesteps: 30
  num_rollouts: 30
  noise_stddev: 1.0
  cost_weight: 0.025
  min_cost: 0.001
  use_noise_adaptation: true
  use_projection: true
```

### 代价函数配置

```yaml
# 平滑性代价
smoothness_cost:
  weight: 0.1

# 碰撞代价
collision_cost:
  weight: 1.0
  kernel_width: 0.05

# 关节限制代价
joint_limit_cost:
  weight: 0.5
```

### 使用规划器

```cpp
// 创建 STOMP 规划器
stomp::StompPlanner planner(robot_model, group_name);

// 设置规划场景
planner.setPlanningScene(planning_scene);

// 设置运动约束
planner.setStartState(start_state);
planner.setGoalConstraints(goal_constraints);

// 执行规划
robot_trajectory::RobotTrajectory trajectory(robot_model, group_name);
bool success = planner.solve(trajectory);

if (success) {
  // 使用优化后的轨迹
  executeTrajectory(trajectory);
}
```

## 调优建议

1. **采样数量**
   - 增加 `num_rollouts` 提高解质量
   - 减少 `num_rollouts` 加快规划速度
   - 典型范围：20-50

2. **噪声水平**
   - 增加 `noise_stddev` 扩大探索范围
   - 减少 `noise_stddev` 精细调优
   - 启用 `use_noise_adaptation` 自适应调整

3. **迭代次数**
   - 增加 `max_iterations` 提高收敛概率
   - 监视代价曲线判断是否需要更多迭代

4. **代价权重**
   - 调整各代价权重平衡不同目标
   - 碰撞代价权重通常设为最高
   - 平滑性代价影响轨迹自然程度

## 高级特性

### 噪声自适应
STOMP 支持根据优化进度自动调整噪声水平：
- 初期：高噪声，广泛探索
- 后期：低噪声，精细调优

### 投影算子
支持将优化后的轨迹投影到满足约束的子空间：
- 关节限制投影
- 碰撞避免投影
- 自定义约束投影

### 自定义代价
支持用户定义自定义代价函数：
- 操作性代价
- 能量消耗代价
- 任务特定代价
