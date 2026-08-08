# ompl

开放运动规划库（OMPL）

## 项目链接

- GitHub: <https://github.com/ompl/ompl>
- 项目主页: https://ompl.kavrakilab.org

## 项目概述

## 项目介绍
OMPL即Open Motion Planning Library，是一款开源的基于采样的运动规划库，主要用于机器人、自动驾驶等领域的路径规划任务，支持在SE(3)、欧几里得空间等20余种状态空间中完成规划。

## 主要特性
1.  内置40余种采样式规划算法，包括RRT-Connect、PRM、KPIECE、RRT*等
2.  支持通过C++和Python扩展自定义规划器与状态空间
3.  集成VAMP实现SIMD加速规划，可在Python和C++环境下实现毫秒级规划
4.  支持跨Linux、macOS、Windows系统部署，提供Python绑定与C++接口。
