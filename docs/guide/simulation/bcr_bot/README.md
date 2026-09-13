# bcr_bot

支持 ROS、ROS2、Gazebo、Ignition、Mujoco 和 ISAAC 仿真平台的移动机器人仿真系统，具备轮式驱动、深度相机、IMU 和 2D LiDAR 功能。

## 项目链接

- GitHub: <https://github.com/blackcoffeerobotics/bcr_bot>
- 项目主页: <https://blackcoffeerobotics.com/blog/migration-from-gazebo-classic-to-ignition-with-ros-2>

## 项目介绍
本项目是一款差分驱动移动机器人的仿真仓库，搭载IMU、深度相机、立体相机和2D LiDAR，支持ROS、ROS2以及Gazebo、Ignition、Mujoco、ISAAC Sim多款仿真引擎。
项目适配多套ROS/仿真环境组合，包括ROS Noetic+Gazebo Classic 11，ROS2 Humble搭配Gazebo Classic 11/Fortress/Harmonic/ISAAC Sim，以及ROS2 Jazzy搭配Gazebo Harmonic/ISAAC Sim/Mujoco Sim。ROS2版本额外支持Nav2和SLAM Tool Box。

## 主要特性
1.  支持多ROS版本与主流仿真引擎的组合部署
2.  搭载多类主流机器人传感器仿真模型
3.  提供完整的依赖安装、编译与运行流程
4.  支持自定义传感器开关、机器人初始位姿、仿真世界等配置参数
5.  适配ROS2导航与SLAM开发流程
