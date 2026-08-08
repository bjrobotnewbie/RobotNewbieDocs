# yertle

一款用于运动研究的3D打印四足机器人 :turtle:

## 项目链接

- GitHub: <https://github.com/Jerome-Graves/yertle>

## 项目概述

## 项目介绍
Yertle是一款3D打印的四足移动研究机器人，可实现从手动调参步态到强化学习（RL）的多种运动控制方案。它支持在PyBullet（CPU）和Isaac Lab（GPU）上训练，通过仿真到现实（sim-to-real）桥接和ROS 2完成部署。
该机器人重约1.8kg，单腿延伸约20cm，标配4个3自由度舵机四肢、ESP32主控，可选配电池、九轴传感器、电流电压传感器以及RPi4单板计算机，续航可达30分钟，整体成本约250英镑，兼容SpotMicro相关配件。

## 主要特性
1.  支持手动调参步态与强化学习两种运动控制方式
2.  支持CPU、GPU多平台训练，可通过sim-to-real和ROS 2快速部署
3.  模块化设计，可选配多种传感器与计算单元
4.  低成本3D打印开源硬件，兼容SpotMicro配件
