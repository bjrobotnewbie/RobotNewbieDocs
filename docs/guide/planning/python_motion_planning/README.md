# python_motion_planning

- 项目链接：https://github.com/ai-winter/python_motion_planning
- 项目主页：https://ai-winter.github.io/python_motion_planning/

## 项目概述

该仓库提供了常见运动规划算法的 Python 实现，包括 N 维网格上的路径规划器、路径跟踪控制器、轨迹优化器，以及基于 matplotlib 的可视化工具和用于测试控制器的简单物理模拟器。

运动规划主要包括路径规划和轨迹规划：
- **路径规划**：基于路径约束（如障碍物），规划机器人在起点和终点之间无冲突行驶的最优路径序列
- **轨迹规划**：基于运动学、动力学约束和路径序列，规划接近全局路径的运动状态

包含的算法：
- 图搜索：Dijkstra、A*、JPS、D*、LPA*、D* Lite、(Lazy)Theta* 等
- 采样搜索：RRT、RRT*、RRT-Connect、有信息 RRT*、Voronoi 等
- 控制器：PID、DWA、APF、LQR、MPC、RPP 等
- 曲线生成：Bezier、Dubins 等

同时提供 ROS C++ 版本和 Matlab 版本，可以通过 pip 直接安装。
