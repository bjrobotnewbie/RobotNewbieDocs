# DynOSAM

DynoSAM：动态物体平滑建图 官方代码发布。论文已被《Transactions on Robotics》（视觉SLAM专刊）接收。这是一个面向动态环境的视觉SLAM框架与流程，可估计物体的运动/位姿及其结构，同时估计相机里程计与静态地图。

## 项目链接

- GitHub: <https://github.com/ACFR-RPG/DynOSAM>
- 项目主页: https://acfr-rpg.github.io/DynOSAM/

## 项目概述

## 项目介绍
DynoSAM是一款面向动态环境的视觉SLAM框架，已被IEEE Transactions on Robotics收录。它支持双目/RGB-D视觉里程计，能够同时估计相机位姿、动态物体的运动与位姿，同时重建静态背景地图与动态物体地图。项目完全集成ROS2，提供全批量、滑动窗口、增量三种优化模式。

## 主要特性
1.  支持动态环境下的完整SLAM流程，可同时输出相机位姿、静态地图与动态物体地图
2.  提供全批量、滑动窗口、增量三种优化方案
3.  完整适配ROS2生态
4.  支持在公开动态SLAM数据集如Oxford Multimotion Dataset以及实采集序列上运行演示
