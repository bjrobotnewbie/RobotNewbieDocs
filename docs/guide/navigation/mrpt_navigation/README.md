# mrpt_navigation

封装了MRPT核心功能的ROS 2节点，涵盖定位、自主导航、rawlog记录等功能。SLAM相关功能位于其他软件包中。

## 项目链接

- GitHub: <https://github.com/mrpt-ros-pkg/mrpt_navigation>
- 项目主页: http://wiki.ros.org/mrpt_navigation

## 项目概述

## 项目介绍
mrpt_navigation是一个ROS 2软件包仓库，将Mobile Robot Programming Toolkit（MRPT）的核心功能封装为ROS 2节点，提供定位、自主导航、原始日志处理等机器人导航相关功能，MRPT的SLAM与传感器访问功能则封装在其他ROS仓库中。该项目兼容ROS 2 Humble、Jazzy、Kilted、Lyrical、Rolling等多个发行版，另有ROS 2 Iron等已终止支持的发行版历史版本。其配套的SLAM框架为MOLA，生成的地图可用于本仓库的定位功能。

## 主要特性
1.  基于ROS 2构建，遵循REP-2003标准定义ROS话题服务质量
2.  封装MRPT核心导航与定位能力，提供如`mrpt_map_server`等节点，可加载ROS标准栅格地图、MRPT或MP2P_ICP地图并发布到指定话题
3.  支持多ROS 2发行版，适配不同Ubuntu系统版本
