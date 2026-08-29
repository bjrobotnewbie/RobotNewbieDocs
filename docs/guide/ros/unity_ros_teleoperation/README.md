# unity_ros_teleoperation

Unity 项目，用于 OpenXR 控制 ROS 系统

## 项目链接

- GitHub: <https://github.com/leggedrobotics/unity_ros_teleoperation>
- 项目主页: <https://rffr.leggedrobotics.com/works/xr/>

## 项目介绍
本项目是一款集成ROS的Unity XR远程操控项目，专为Quest 3 VR头显设计，支持OpenXR、手部追踪与Unity输入系统，适配Unity 6000.2.15f1版本，是ROS 1系统下官方支持的最新Unity版本。项目可运行于Linux x64与Quest 3平台，提供了完整的Unity与VR设备部署流程，支持ROS1与ROS2系统。

## 主要特性
1.  支持ROS网络双向通信，需搭配ROS-TCP-Endpoint节点使用，可直接部署在机器人设备上
2.  提供音频流组件，实现基于ROS的双向音频传输
3.  提供快速部署脚本与多平台配置文档，支持侧载安装与Linux设备串流
4.  支持自定义机器人模型扩展，可适配不同的远程操控机器人场景
5.  采用BSD-3-Clause开源协议，支持社区贡献与二次开发
