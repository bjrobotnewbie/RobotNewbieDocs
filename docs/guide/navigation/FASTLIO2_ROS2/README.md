# FASTLIO2_ROS2

ROS2 / FAST_LIO / PGO / 在线重定位 / 一致地图（使用 BA 或 HBA）

## 项目链接

- GitHub: <https://github.com/liangheming/FASTLIO2_ROS2>

## 项目概述

## 项目介绍
本项目是针对FASTLIO2的ROS2适配重构版本，在原FASTLIO基础上新增了回环检测、在线重定位和一致性地图优化功能，支持小场景BA优化和大场景HBA优化，可用于激光SLAM建图与定位任务。

## 主要特性
1.  完成FASTLIO2的ROS2版本重构
2.  集成基于位置先验+ICP的回环检测，搭配GTSAM实现位姿图优化
3.  提供两阶段ICP的在线重定位功能
4.  支持小场景BLAM和大场景HBA两种一致性地图优化方案
5.  适配Ubuntu22.04 + ROS2 Humble环境，依赖PCL、Eigen、Sophus、GTSAM等库
