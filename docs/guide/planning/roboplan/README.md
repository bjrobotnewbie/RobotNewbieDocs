# roboplan

- 项目链接：https://github.com/open-planning/roboplan
- 项目主页：https://roboplan.readthedocs.io

## 项目概述

roboplan 是一个**基于 Pinocchio 的现代机器人运动规划库**，用 C++ 编写，提供模块化的运动规划组件。

这是一个实验性的开发中项目，目标是提供现代化、模块化的机器人运动规划基础设施。

### 主要模块

- **roboplan**：核心 C++ 库
- **roboplan_simple_ik**：简单逆运动学（IK）求解器
- **roboplan_oink**：基于任务的最优逆运动学（OInK）求解器
- **roboplan_rrt**：基于快速扩展随机树（RRT）的运动规划器
- **roboplan_toppra**：TOPP-RA 轨迹时间参数化算法的封装
- **roboplan_example_models**：包含用于测试和示例的机器人模型
- **roboplan_examples**：真实机器人模型的基础示例

### 特点

- **模块化设计**：各个组件独立，可以单独使用
- **基于 Pinocchio**：利用 Pinocchio 进行高效的运动学和动力学计算
- **现代 C++**：代码结构清晰，易于集成
- **支持多机器人**：支持双机械臂等多机器人系统规划

roboplan 正在积极开发中，致力于为机器人运动规划提供现代化的开源基础设施。
