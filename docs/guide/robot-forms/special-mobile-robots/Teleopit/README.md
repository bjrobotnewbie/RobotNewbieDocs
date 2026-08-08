# Teleopit

完整的人形机器人遥操作系统

## 项目链接

- GitHub: <https://github.com/BotRunner64/Teleopit>
- 项目主页: <https://botrunner64.github.io/Teleopit/>

## 项目概述

## 项目介绍
Teleopit是一款轻量可扩展的类人机器人全身遥操作框架，可实现从BVH动作文件或Pico 4 VR设备到Unitree G1类人机器人的实时运动重定向，支持在MuJoCo仿真环境或真实硬件上运行。

## 主要特性
1.  支持BVH文件、Pico 4 VR两种输入源，完成跨平台实时运动重定向
2.  兼容MuJoCo仿真与真实硬件部署，提供sim2sim、sim2real多种运行模式
3.  支持Unitree G1多型号机器人模型，配套官方匹配的控制策略权重
4.  新增支持OpenNeck颈部控制、LinkerHand手部姿态控制、Pico HMD主动视觉映射等外设扩展
5.  搭载高可靠的主机高层策略sim2real运行时，采用msgpack/ZeroMQ协议，支持50Hz速率受限的时间戳对齐调度与异步滚动重规划
6.  配套完整的录制、回放与可视化工具，支持同步录制动作数据与视频
