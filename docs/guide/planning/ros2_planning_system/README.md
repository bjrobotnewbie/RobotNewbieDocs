# ros2_planning_system (PlanSys2)

- 项目链接：https://github.com/PlanSys2/ros2_planning_system

## 项目概述

PlanSys2 (ROS2 Planning System) 是为 ROS2 提供的**基于 PDDL 的自动规划系统**，目标是为机器人开发者提供可靠、简单、高效的自动规划框架。

该项目受到 ROSPlan 的启发，在迁移到 ROS2 的同时，改进了易用性、效率，并添加了新工具。

### 核心特点

- **基于 PDDL**：使用 PDDL (Planning Domain Definition Language) 进行问题域描述
- **完全集成 ROS2**：遵循 ROS2 最佳实践，支持最新 ROS2 版本（Humble、Iron、Jazzy 等）
- **模块化架构**：规划问题域、域知识、规划器、执行器等模块分离
- **易用性**：提供清晰的 API 和完整文档，方便集成到项目
- **终端工具**：提供交互式终端方便调试和测试

### 主要组件

- **plansys2_domain_expert**：管理规划问题域
- **plansys2_problem_expert**：管理问题实例和知识
- **plansys2_planner**：调用外部规划器（POPF、FF 等）求解计划
- **plansys2_executor**：执行计划，监控执行状态
- **plansys2_terminal**：交互式调试终端

PlanSys2 让自动规划技术更容易集成到机器人项目中，特别适用于任务规划、高层行为决策等场景。
