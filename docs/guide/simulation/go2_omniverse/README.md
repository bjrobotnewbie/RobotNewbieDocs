# go2_omniverse

支持宇树Unitree Go2、Unitree G1机器人的Nvidia Isaac Lab（Isaac Gym / Isaac Sim）

## 项目链接

- GitHub: <https://github.com/abizovnuralem/go2_omniverse>

## 项目概述

## 项目介绍
本项目是Unitree Go2、G1机器人的数字孪生项目，适配Nvidia Isaac Lab（Isaac Gym / Isaac Sim），可用于机器人算法的仿真研发与测试。项目支持Isaac Sim 5.x与ROS 2 Jazzy，提供了实机-仿真数字孪生模式，可将物理机器人的状态同步到仿真环境中，实现1:1镜像复现。

## 主要特性
1.  **实机孪生模式**：通过`twinbot_bridge.py`转发物理机器人的`/lowstate`数据流，将真实机器人的关节状态同步到仿真Go2中，支持IMU对齐的运动复现，可实现真实到仿真的状态同步。
2.  **高保真渲染**：默认使用Isaac内置的工作室HDRI环境光照，支持RT2高质量渲染预设，可实现带真实反射效果的仿真画面，还支持无头渲染导出静态效果图与动态镜头素材。
3.  适配最新版本的Isaac开发工具链，兼容Python 3.10/3.11与Ubuntu 22.04系统，采用BSD-2开源协议。
