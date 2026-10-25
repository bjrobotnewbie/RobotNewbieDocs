# aruco_ros

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/aruco_ros/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Aruco 增强现实标记检测库的软件包及 ROS 封装

## 项目链接

- GitHub: <https://github.com/pal-robotics/aruco_ros>

## 项目介绍
aruco_ros是Aruco增强现实（AR）标记检测器库的软件包及ROS封装，用于在ROS环境中实现AR标记的检测与跟踪，支持在机器人平台（如REEM）上完成相关视觉任务。

## 主要特性
- 支持AR标记的高帧率跟踪，可生成指定尺寸、感知歧义性最小的AR标记（适用于多标记跟踪场景）
- 提供基于标记板的高精度跟踪能力
- 包含ROS封装，提供`aruco_ros/Marker.msg`、`aruco_ros/MarkerArray.msg`等消息类型，支持标记位姿的发布与可视化
- 应用场景涵盖物体位姿估计、视觉伺服（同时跟踪物体与手部）等任务，可通过ROS Launch文件快速在仿真环境中测试使用。
