# genz-icp

GenZ-ICP：SOTA 鲁棒激光雷达里程计（IEEE RA-L 2025）

## 项目链接

- GitHub: <https://github.com/cocel-postech/genz-icp>

## 项目概述

## 项目介绍
GenZ-ICP是一款发表于IEEE RA-L 2025的前沿鲁棒LiDAR里程计方案，主打可泛化且抗退化的激光SLAM能力，通过自适应加权策略提升算法鲁棒性。项目支持C++、Python开发环境，兼容ROS1与ROS2，可通过`pip install genz-icp`快速安装，也提供了完整的ROS部署包。

## 主要特性
1.  顶尖性能：当前SOTA级别的鲁棒激光里程计算法
2.  多语言支持：提供C++、Python两种实现，支持pip快速部署
3.  全ROS生态兼容：适配ROS1与ROS2，可直接集成到机器人开发流程
4.  开箱即用：提供标准数据加载器与命令行运行工具，支持快速测试与部署
5.  抗退化设计：针对激光SLAM常见的退化场景优化，提升复杂环境下的定位精度与稳定性
