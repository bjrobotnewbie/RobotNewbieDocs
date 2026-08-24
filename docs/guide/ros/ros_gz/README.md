# ros_gz

ROS (1 和 2) 与 Gazebo 仿真之间的集成

## 项目链接

- GitHub: <https://github.com/gazebosim/ros_gz>
- 项目主页: <https://gazebosim.org>

## 项目概述

## 项目介绍
本项目是ROS（1和2）与Gazebo仿真的集成工具包，实现两者之间的通信桥接，支持将Gazebo仿真数据流转至ROS，或反向转发ROS指令到Gazebo仿真环境。可用于机器人仿真开发、SLAM算法验证、RL机器人训练等场景。

## 主要特性
1.  提供多版本兼容适配，针对不同ROS 2发行版和Gazebo版本提供对应分支与安装源
2.  包含核心元包`ros_gz`以及图像传输桥接包`ros_gz_image`等工具组件
3.  兼容旧版`ros_ign`前缀包，推荐直接使用`ros_gz`系列包
4.  ROS 1版本兼容性可参考noetic分支文档
