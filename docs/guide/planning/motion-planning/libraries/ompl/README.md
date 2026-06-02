# OMPL (Open Motion Planning Library)

OMPL 是一个开源的运动规划库，实现了大量基于采样的运动规划算法。它是 MoveIt! 和 MoveIt 2 的默认规划器后端，被广泛应用于机器人研究和工业应用。

## 简介

OMPL（Open Motion Planning Library）是一个高性能的 C++ 运动规划库，专注于基于采样的规划算法。它提供了灵活的接口和丰富的算法实现，支持高维构型空间的运动规划。

## 核心特性

### 算法丰富
- 支持多种基于采样的规划算法
- 提供优化和路径简化工具
- 支持自定义状态空间和有效性检查

### 高性能
- 纯 C++ 实现，性能优秀
- 支持多线程规划
- 内存占用低

### 灵活可扩展
- 模块化设计，易于扩展
- 支持自定义状态空间
- 插件式架构

## 主要算法

### 单查询规划器
- **RRT** - 快速扩展随机树
- **RRT*** - 渐近最优 RRT
- **RRT-Connect** - 双向 RRT
- **EST** - 扩展空间树
- **SBL** - 单查询双向树
- **KPIECE** - 基于网格的探索
- **LazyPRM** - 懒惰概率路线图

### 多查询规划器
- **PRM** - 概率路线图
- **PRM*** - 渐近最优 PRM

### 控制规划器
- **KPIECE** - 带控制约束
- **RRT** - 带动力学约束

## 项目链接

- 官方网站: https://ompl.kavrakilab.org/
- GitHub 仓库: https://github.com/ompl/ompl
- 官方文档: https://ompl.kavrakilab.org/core/
- API 文档: https://ompl.kavrakilab.org/api_overview.html

## 与 MoveIt! 集成

OMPL 是 MoveIt! 的默认规划器，通过 OMPL 规划器插件提供以下功能：

- 配置化的规划算法选择
- 规划时间和质量参数调优
- 多规划器混合使用
- 规划请求适配器支持

## 应用场景

- 机械臂运动规划
- 移动机器人导航
- 人形机器人运动
- 多机器人系统
- 研究与教育

## 快速开始

```cpp
#include <ompl/base/SpaceInformation.h>
#include <ompl/base/spaces/SE3StateSpace.h>
#include <ompl/geometric/planners/rrt/RRT.h>

namespace ob = ompl::base;
namespace og = ompl::geometric;

// 创建 SE(3) 状态空间
auto space(std::make_shared<ob::SE3StateSpace>());

// 设置空间边界
ob::RealVectorBounds bounds(3);
bounds.setLow(-1);
bounds.setHigh(1);
space->setBounds(bounds);

// 创建空间信息
auto si(std::make_shared<ob::SpaceInformation>(space));
si->setStateValidityChecker(isStateValid);
si->setup();

// 定义问题
ob::ProblemDefinition pdef(si);
pdef.setStartAndGoalStates(start, goal);

// 创建 RRT 规划器
auto planner(std::make_shared<og::RRT>(si));
planner->setProblemDefinition(pdef);
planner->setup();

// 求解规划问题
ob::PlannerStatus solved = planner->ob::Planner::solve(1.0);
```
