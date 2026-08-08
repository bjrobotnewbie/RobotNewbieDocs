# isaac_ros_visual_slam

基于NVIDIA加速cuVSLAM的视觉SLAM/里程计开发包

## 项目链接

- GitHub: <https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_visual_slam>
- 项目主页: https://developer.nvidia.com/isaac-ros-gems

## 项目概述

## 项目介绍
本项目是基于NVIDIA加速cuVSLAM的ROS 2视觉SLAM/里程计包，支持立体视觉惯性里程计(SVIO)。它可通过一个或多个立体相机+可选IMU，为移动机器人、无人机提供实时低延迟的位姿估计，作为导航输入的里程计源，尤其适用于GPS不可用的场景如室内、城市高楼遮挡区域。

## 主要特性
1.  基于NVIDIA GPU加速，实现高帧率实时运算
2.  支持立体相机+IMU的视觉惯性里程计方案，在特征不足时可依靠IMU补充位姿估计
3.  可作为移动机器人辅助里程计，或是无人机的主里程计来源
4.  通过优化关键点匹配与重投影误差，实现高精度定位建图
