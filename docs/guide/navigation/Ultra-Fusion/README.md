# Ultra-Fusion

Ultra-Fusion：传感器退化与时空扰动下的鲁棒紧耦合多传感器融合SLAM框架

## 项目链接

- GitHub: <https://github.com/sjtuyinjie/Ultra-Fusion>
- 项目主页: https://sjtuyinjie.github.io/ultrafusion-web/

## 项目概述

## 项目介绍
Ultra-Fusion是一款面向智能交通系统的紧耦合多传感器融合SLAM框架，针对传感器退化（光照不佳、LiDAR退化、车轮打滑、GNSS失效）和时空标定失准的真实部署场景设计。
该框架支持ROS1 Noetic和ROS2 Humble，可适配地面、腿式、空中多种移动平台，兼容RGB-D、LiDAR、IMU、轮式里程计、GNSS等多类传感器。

## 主要特性
1.  统一可配置优化框架，支持WIO、VIO、LIO、LVIO多种融合模式，可按需添加轮式/GNSS融合与在线标定
2.  提供多版本发布：ROS1 Noetic基础版与全向多相机版本UFO，ROS2 Humble适配版
3.  配套官方数据集M3DGR、演示视频与预编译二进制包，可快速复现论文基准测试
4.  具备在复杂传感器异常场景下的鲁棒运行能力
