# multi_uav_simulator

Mavswarm 是基于 ROS 的轻量多无人机仿真器，支持异构四旋翼集群、控制和轨迹规划实验。

## 项目链接

- GitHub: <https://github.com/malintha/multi_uav_simulator>

## 项目概述

multi_uav_simulator 提供一个轻量快速的多飞行器仿真环境，可在单台桌面机器上模拟最多约 10 架异构四旋翼并包含物理效果。项目支持四旋翼控制、轨迹优化和 receding horizon planning，内置 Lee 几何跟踪控制器，并可通过 YAML 配置增加新的四旋翼模型参数。

该项目主要面向 ROS1 环境，同时 README 提醒可查看 ros2 分支中的 mavswarm2。它适合无人机集群控制、轨迹优化、编队和规划算法的研究原型，尤其适合需要比大型高保真模拟器更轻量、安装和运行成本更低的 ROS 无人机集群实验。
