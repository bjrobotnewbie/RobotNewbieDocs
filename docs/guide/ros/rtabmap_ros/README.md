# rtabmap_ros

rtabmap_ros 是 RTAB-Map 的 ROS/ROS 2 包，用于 RGB-D、立体和激光雷达 SLAM 与定位建图。

## 项目链接

- GitHub: <https://github.com/introlab/rtabmap_ros>
- 项目主页: http://wiki.ros.org/rtabmap_ros

## 项目概述

rtabmap_ros 将 RTAB-Map 的库和独立应用接入 ROS 生态，提供同步建图、回环检测、定位、图优化、点云/栅格地图输出和多传感器输入支持。它可用于移动机器人、RGB-D 相机、双目相机和激光雷达平台，在 ROS 1 与 ROS 2 中都有构建和二进制包支持。

项目的主要价值是把成熟的 RTAB-Map SLAM 算法包装为 ROS 节点、launch 和参数化接口，方便用户直接接入机器人传感器、TF、里程计和导航栈。它适合室内外移动机器人建图、视觉/激光融合 SLAM、长期定位和多传感器三维重建应用。
