# se3-lio

SE(3)-LIO：基于 SE(3) 流形上联合分布姿态的平滑 IMU 传播方法，用于实现精确且鲁棒的激光雷达 - 惯性里程计（ICRA 2026）

## 项目链接

- GitHub: <https://github.com/url-kaist/se3-lio>
- 项目主页: <https://se3-lio.github.io/>

## 项目介绍
SE(3)-LIO是一款基于SE(3)流形联合分布位姿实现平滑IMU传播的高精度鲁棒LiDAR-惯性里程计方案，已被ICRA 2026收录。项目支持ROS1 Noetic和ROS2 Humble，提供了Docker一键部署环境，包含ROS无关的C++核心库以及对应ROS版本的节点、启动配置文件。

## 主要特性
1.  基于SE(3)流形的平滑IMU传播，实现精准鲁棒的激光惯性里程计
2.  兼容多类型LiDAR，支持Ouster、Hesai、Livox系列传感器
3.  提供ROS1和ROS2双版本部署方案，附带完整的启动、配置和RViz可视化文件
4.  支持通过Docker快速构建运行环境，降低部署门槛
5.  附带Python CLI工具与基准测试配置文件，方便算法验证
