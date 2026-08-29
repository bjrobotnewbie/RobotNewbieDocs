# unitree_go2_ros2

该包提供了基于 CHAMP 控制器框架的完整 ROS 2 Jazzy 集成，用于 Unitree Go2 四足机器人。

## 项目链接

- GitHub: <https://github.com/khaledgabr77/unitree_go2_ros2>

## 项目介绍
本项目是针对Unitree Go2四足机器人的完整ROS 2 Jazzy集成包，基于CHAMP控制器框架开发。适配了专属配置包和ROS 2机器人描述模型，可实现该四足机器人的仿真、控制与自主作业功能。Unitree Go2是宇树科技出品的四足机器人，适用于科研与商用场景，搭载高性能执行器与先进传感器，可适配多种地形。CHAMP是开源四足机器人开发框架，采用分层控制系统，结合模式调制与阻抗控制实现高效运动。

## 主要特性
1.  完整的ROS 2 Jazzy适配集成
2.  适配ROS 2控制框架的URDF机器人模型
3.  支持Gazebo Harmonic仿真
4.  支持键盘遥控、RVIZ可视化
5.  集成步态控制与配置功能
6.  已支持的仿真传感器：IMU、2D Hokuyo LiDAR、3D Velodyne LiDAR、4D L1 LiDAR（待优化）、单目相机、GPS（水平精度约0.5m），深度相机待开发
7.  支持RVIZ点云可视化，提供多种传感器配置方案
8.  完整SLAM功能、Nav2导航集成功能正在开发中

系统要求：Ubuntu 24.04、ROS 2 Jazzy、Gazebo Sim Harmonic。
