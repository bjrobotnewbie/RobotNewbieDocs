# habitat-gs

[ECCV 2026] Habitat-GS: 基于动态高斯Splatting的高保真导航模拟器

## 项目链接

- GitHub: <https://github.com/zju3dv/habitat-gs>
- 项目主页: https://zju3dv.github.io/habitat-gs/

## 项目概述

## 项目介绍
Habitat-GS是一款被ECCV 2026收录的高保真导航模拟器，基于动态高斯溅射（Gaussian Splatting）技术构建。项目提供了配套的高质量3DGS场景数据集，当前已包含129个室内场景，同时支持将原始3DGS场景快速转换为可用于导航仿真的环境。

## 主要特性
1.  支持基于动态高斯溅射的高保真视觉仿真，还原真实场景渲染效果
2.  配套提供扩展的3DGS场景数据集，包含训练与评估所需的场景、任务episode与轨迹数据
3.  内置浏览器端NavMesh编辑工具，可直接在3DGS场景上绘制可通行区域，一键生成Habitat可用的导航网格，实现从3DGS场景到导航仿真的闭环流程
4.  可用于机器人导航、SLAM、强化学习（RL）等相关算法的训练与评估。
