# mrpt_slam

MRPT 中的 SLAM 算法 ROS 封装

## 项目链接

- GitHub: <https://github.com/mrpt-ros-pkg/mrpt_slam>
- 项目主页: <http://wiki.ros.org/mrpt_slam>

## 项目概述

## 项目介绍
本项目是`mrpt_slam`，为Mobile Robot Programming Toolkit（MRPT）中的SLAM算法提供ROS封装包，适配ROS Kinetic、Melodic等版本，可在Ubuntu 16.04、18.04系统下运行。官方文档可参考ROS Wiki：http://wiki.ros.org/mrpt_slam。

项目有两个主要分支：
1.  `master`分支：适配最新版MRPT（≥1.5.4、≥1.9.9）
2.  `compat-mrpt-1.3`存档分支：用于兼容MRPT 1.3.x及更旧版本

## 主要特性
1.  基于成熟的MRPT库实现SLAM算法，通过ROS封装提供标准ROS接口
2.  适配多ROS版本与Ubuntu系统，已通过Travis CI与ROS构建农场的持续集成测试
3.  提供稳定的发布版本与开发版本构建支持
