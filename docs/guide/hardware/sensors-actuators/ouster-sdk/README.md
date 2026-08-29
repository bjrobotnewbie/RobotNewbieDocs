# ouster-sdk

跨平台 C++ 和 Python SDK，用于 Ouster LiDAR 传感器。包含可视化工具、数据记录/回放及传感器配置工具。

## 项目链接

- GitHub: <https://github.com/ouster-lidar/ouster-sdk>
- 项目主页: <https://ouster.com>

## 项目介绍
本项目是Ouster激光雷达传感器的跨平台C++和Python开发SDK，用于连接、配置Ouster传感器，读取并可视化其点云数据。同时提供数据录制、回放工具，支持OSF格式传感器数据存储。
项目包含多个核心模块：核心C++库、感知与建图算法库、PCAP处理库、OSF数据存储库、可自定义点云可视化工具，以及PyPI可安装的Python SDK包。
官方ROS驱动已迁移至独立仓库，可通过对应仓库文档快速上手。

## 主要特性
1.  跨平台兼容，支持C++和Python两种开发语言
2.  完整覆盖传感器连接配置、数据读取、可视化全流程
3.  提供点云可视化工具、数据录制回放能力，支持OSF标准数据格式
4.  可通过PyPI快速安装Python版本SDK包
5.  配套官方文档与社区支持渠道，采用BSD 3-Clause开源协议
