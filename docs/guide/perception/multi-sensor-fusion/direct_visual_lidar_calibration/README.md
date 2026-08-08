# direct_visual_lidar_calibration

一个用于无靶标LiDAR-相机标定的工具箱 [ROS1/ROS2]

## 项目链接

- GitHub: <https://github.com/koide3/direct_visual_lidar_calibration>
- 项目主页: https://koide3.github.io/direct_visual_lidar_calibration/

## 项目概述

## 项目介绍
这是一个面向ROS1/ROS2的无靶标激光雷达-相机外参标定工具箱，仅需一组或多组激光点云和相机图像数据，即可自动完成两者的外参校准，无需初始猜测值。

## 主要特性
1.  **通用性强**：支持多种激光雷达（旋转式、非重复扫描式）和相机投影模型（针孔、鱼眼、全向相机）
2.  **无靶标**：无需专用标定板，利用环境结构和纹理完成标定
3.  **单帧即可标定**：最少仅需一组数据，多组数据可提升标定精度
4.  **全自动流程**：无需手动提供初始参数
5.  **高精度高鲁棒性**：采用像素级直接激光-相机配准算法，优于基于边缘的间接配准方案

该工具箱附带完整文档、Docker镜像，已在ICRA2023发表相关论文。
