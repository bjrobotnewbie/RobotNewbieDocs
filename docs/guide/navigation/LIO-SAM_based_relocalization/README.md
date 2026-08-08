# LIO-SAM_based_relocalization

本系统开发了一个可基于构建地图重新定位机器人的简单系统。该系统基于 LIO-SAM。

## 项目链接

- GitHub: <https://github.com/chennuo0125-HIT/LIO-SAM_based_relocalization>

## 项目概述

## 项目介绍
本项目基于LIO-SAM（未融合GPS的原始版本）开发了一款简易的机器人重定位系统，可以让机器人在已构建的地图中实现定位。

## 主要特性
1.  基于LIO-SAM框架实现机器人重定位
2.  支持通过ROS启动相关节点，可通过rosbag播放测试数据
3.  初始化阶段需要手动在Rviz中提供初始位姿猜测，建议初始化过程中保持机器人静止，播放bag包时可先播放0.5秒后暂停直至初始化完成

## 使用场景
适用于基于LIO-SAM建图后的机器人重定位任务，可快速在已构建的激光SLAM地图中恢复机器人位姿。
