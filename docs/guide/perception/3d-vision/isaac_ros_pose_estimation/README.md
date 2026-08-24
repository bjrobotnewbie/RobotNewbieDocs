# isaac_ros_pose_estimation

深度学习的 NVIDIA 加速 3D 物体姿态估计

## 项目链接

- GitHub: <https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_pose_estimation>
- 项目主页: <https://developer.nvidia.com/isaac-ros-gems>

## 项目概述

## 项目介绍
本项目是NVIDIA推出的基于深度学习、搭载GPU加速的3D物体位姿估计工具包，属于Isaac ROS生态，包含3个ROS 2软件包，可通过感知功能结合深度信息输出物体3D位姿，用于导航或机械臂操作场景。
其中`isaac_ros_foundationpose`基于NVLabs的FoundationPose预训练模型，支持零样本新物体位姿估计与跟踪，无需微调；`isaac_ros_dope`为成熟稳定的快速方案；`isaac_ros_centerpose`支持TAO工具链，精度表现较好。

## 主要特性
1.  支持三种不同定位方案，可根据需求在易用性、速度、精度间选择
2.  全部基于DNN的GPU加速推理，性能高效
3.  可输出物体3D位姿，适配机器人导航、机械臂抓取等感知场景
4.  FoundationPose方案可直接识别全新物体，无需额外训练微调
