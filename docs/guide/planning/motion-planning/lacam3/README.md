# lacam3

LaCAM*：面向实时、大规模及近乎最优的多智能体路径规划（AAMAS-24）

## 项目链接

- GitHub: <https://github.com/Kei18/lacam3>
- 项目主页: <https://kei18.github.io/lacam3/>

## 项目概述

## 项目介绍
本项目是AAMAS 2024论文《Engineering LaCAM*: Towards Real-Time, Large-Scale, and Near-Optimal Multi-Agent Pathfinding》的官方代码库，是LaCAM系列多智能体路径规划（MAPF）算法的第三代版本。
该算法属于基于搜索的MAPF解决方案，可高效处理超1000个智能体的大规模实例，支持实时规划且结果接近最优。项目提供C++原生实现，同时支持通过Python调用，还兼容第三方MAPF可视化工具。

## 主要特性
1.  **高性能大规模规划**：可快速处理千级以上智能体的路径规划任务
2.  **近最优解**：规划结果接近全局最优路径
3.  **多语言支持**：原生C++17实现，提供Python绑定接口
4.  **完整工具链**：内置编译脚本、运行示例、实验脚本以及MAPF可视化兼容支持
5.  支持自定义超参数，默认配置可满足多数常规场景需求
