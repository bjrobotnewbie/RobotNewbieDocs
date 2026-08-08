# mesh_navigation

Mesh Navigation Stack：非平坦地形下的高效移动机器人导航

## 项目链接

- GitHub: <https://github.com/naturerobots/mesh_navigation>
- 项目主页: https://naturerobots.github.io/mesh_navigation_docs/

## 项目概述

## 项目介绍
mesh_navigation（MeshNav）是一款面向移动机器人的3D网格导航栈，专为非平坦地形的高效导航设计。它基于三角形网格表示2D流形环境，通过可扩展的分层网格地图，支持在复杂户外场景中实现安全导航。该项目兼容ROS 2 Humble和Jazzy版本，已集成Move Base Flex，提供通用的ROS动作接口用于路径规划、运动控制和故障恢复，同时附带可在分层网格地图上运行的规划器和控制器插件。

## 主要特性
1.  基于3D三角形网格构建导航环境，适配非平坦地形
2.  模块化分层网格地图，支持通过插件加载地形几何、语义等多维度指标
3.  集成Move Base Flex，提供标准ROS导航动作接口
4.  内置适配网格地图的专用规划与控制插件
5.  支持复杂户外障碍物环境下的路径与运动规划
