# dynoplan

Dynoplan 是一个用于求解动力学约束运动规划问题的小型库，围绕 Dynobench 定义的问题集实现多种规划算法。

## 项目链接

- GitHub: <https://github.com/quimortiz/dynoplan>
- 项目主页: https://quimortiz.github.io/idbastar

## 项目概述

Dynoplan 面向 kinodynamic motion planning，即同时考虑机器人运动学和动力学约束的运动规划问题。与只关注几何可达性的路径规划不同，这类问题需要生成满足系统动力学、控制约束和轨迹可执行性的运动方案，适合研究无人车、四旋翼、欠驱动系统等更真实的机器人规划场景。

项目基于 Dynobench 中定义的机器人和问题模型，主要实现了三类规划思路：带几何初始猜测的轨迹优化 RRT*-TO、基于采样的 SST*，以及结合搜索与优化的 iDb-A*。README 中还提到后续会扩展更多 db-RRT、AO-db-RRT、DB-SST 等相关方法。轨迹优化部分依赖 Crocoddyl，采样规划部分依赖 OMPL，因此它更偏研究型和算法实验型工具。

Dynoplan 适合用于动力学运动规划算法比较、Benchmark 实验和研究复现。仓库提供测试示例、编译说明、运动基元下载与生成方式，用户可以通过现有 Dynobench 系统快速运行实验，也可以为新系统实现动力学模型并生成对应运动基元。
