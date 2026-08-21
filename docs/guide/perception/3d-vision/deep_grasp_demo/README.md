# deep_grasp_demo

MoveIt 框架内的抓取检测深度学习方法

## 项目链接

- GitHub: <https://github.com/PickNikRobotics/deep_grasp_demo>
- 项目主页: <https://picknik.ai/>

## 项目概述

## 项目介绍
本项目是基于深度学习的抓取检测演示仓库，可在MoveIt任务构造器中实现抓取位姿生成，适配Ubuntu 18.04 + ROS Melodic环境。项目包含三个功能包，分别集成不同的深度学习抓取方案，用于机械臂拾取放置任务流程搭建。

## 主要特性
1.  支持两种主流深度学习抓取方案：
    - 基于GPD的点云抓取位姿采样
    - 基于Dex-Net的深度图像抓取位姿采样
2.  提供可直接在MoveIt任务构造器中调用的抓取生成任务模块，快速搭建拾取放置流水线
3.  配套完整的安装部署教程与演示启动流程。
