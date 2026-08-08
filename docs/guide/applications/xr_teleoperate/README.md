# xr_teleoperate

本仓库实现了基于 XR 设备的 Unitree 人形机器人远程操控。

## 项目链接

- GitHub: <https://github.com/unitreerobotics/xr_teleoperate>

## 项目概述

## 项目介绍
本项目实现了基于Apple Vision Pro的Unitree H1_2人形机器人遥操作系统，支持通过XR设备远程操控宇树人形机器人完成相关动作。项目测试环境为Ubuntu 20.04和22.04，可参考官方文档和OpenTeleVision项目完成相关配置。

## 主要特性
1.  支持Apple Vision Pro作为XR操控终端，实现人形机器人远程遥操作
2.  提供仿真环境遥操作示例，可基于Isaac Gym完成模拟测试
3.  包含完整的环境配置流程，涵盖逆运动学依赖、unitree_dds_wrapper、TeleVision等组件安装
4.  提供本地局域网部署方案，支持通过自签名证书完成VisionPro端的安全连接与WebXR调试。
