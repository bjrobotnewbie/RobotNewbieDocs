# ellipselio

EllipseLIO 是一种具有椭圆表示的自适应激光雷达惯导方法。

## 项目链接

- GitHub: <https://github.com/v4rl-ucy/ellipselio>
- 项目主页: <https://v4rl-ucy.github.io/ellipselio/>

## 项目概述

## 项目介绍
EllipseLIO是一款采用椭球表示的自适应LiDAR惯性里程计方案，基于ROS2开发，支持Linux系统，采用MIT开源协议。该项目可用于激光雷达与惯性测量单元融合的位姿估计，支持离线数据包回放和实时传感器数据输入，已在多个公开数据集上完成适配。

## 主要特性
1.  采用椭球表示的自适应LiDAR惯性里程计算法
2.  支持ROS2 Humble和Jazzy版本
3.  适配Newer College、Oxford Spires、BotanicGarden、GEODE、GRACO等多个公开数据集，提供预设配置文件
4.  支持离线bag包运行和实时传感器数据采集两种运行模式
5.  可通过YAML配置文件独立控制发布的输出内容
