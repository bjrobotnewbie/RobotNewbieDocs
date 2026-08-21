# hei-rebot-lift

HEI ReBot Lift 是一款基于 LeRobot/ReBot 的双臂移动机器人，配备升降平台、全向底盘、三目视觉以及 VR + MuJoCo + Pinocchio 的逆向运动学（IK）远程操作管道。它支持远程操作、数据记录、ACT/VLA 训练以及策略部署。

## 项目链接

- GitHub: <https://github.com/lipengdong/hei-rebot-lift>

## 项目概述

## 项目介绍
HEI ReBot Lift是一款基于LeRobot/ReBot的双臂升降移动机器人项目，面向具身AI学习、复现与实机验证，旨在降低搭建真实机器人学习系统的门槛。项目采用完全开源可复现的模式，提供硬件物料、接线、部署流程、VR遥操作管线、数据集录制、ACT/VLA训练以及实机部署全流程支持。机器人硬件包含双臂、升降平台、四轮O型全向底盘和三个摄像头，软件基于LeRobot构建，覆盖MuJoCo/Pinocchio逆运动学、LeRobotDataset、模仿学习以及VLA策略部署。

## 主要特性
1.  **双臂协作操作**：搭载达妙双臂与夹爪，支持遥操作、数据录制与策略部署
2.  **升降平台**：开机自动归位，可自定义升降上限
3.  **全向移动底盘**：四轮O型结构，支持x/y/theta三轴速度控制
4.  **VR遥操作管线**：通过Telegrip采集VR控制器数据，结合MuJoCo+Pinocchio/CasADi计算逆运动学
5.  **三摄像头视觉输入**：包含前置、左右腕部共三路视觉数据
