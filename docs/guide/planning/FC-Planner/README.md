# FC-Planner

FC-Planner 是一个面向复杂三维场景快速空中覆盖的骨架引导全局规划框架，曾入围 ICRA 2024 最佳无人机论文。

## 项目链接

- GitHub: <https://github.com/HKUST-Aerial-Robotics/FC-Planner>
- 项目主页: https://hkust-aerial-robotics.github.io/FC-Planner/

## 项目概述

FC-Planner 是面向无人机三维覆盖任务的全局规划框架，全名为 “A Skeleton-guided Planning Framework for Fast Aerial Coverage of Complex 3D Scenes”。它关注大规模、复杂三维环境中的快速覆盖问题，例如无人机需要高效观察或重建复杂空间结构时，如何生成覆盖充分且执行效率高的飞行路径。

项目方法以场景骨架为引导，将复杂三维环境的结构信息转化为规划线索，从而降低全局覆盖规划难度。README 和项目主页展示了仿真与真实实验结果，并强调该方法相对已有方案具有系统简单、性能较好和适合大场景覆盖等优势。项目还与多无人机自主重建方向的后续工作 SOAR 有关联。

FC-Planner 适合无人机自主覆盖、三维场景重建、复杂环境巡检和空中机器人路径规划研究。仓库提供论文、项目主页、演示视频和代码实现，适合用于论文复现、实验对比和进一步扩展到多无人机覆盖规划任务。