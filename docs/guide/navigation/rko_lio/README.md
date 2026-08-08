# rko_lio

无需传感器特定建模的稳健激光雷达-惯性里程计方法

## 项目链接

- GitHub: <https://github.com/PRBonn/rko_lio>
- 项目主页: https://prbonn.github.io/rko_lio/

## 项目概述

## 项目介绍
RKO-LIO是一款无需传感器专属建模的鲁棒LiDAR-Inertial Odometry（LIO）方案，由德国波恩大学PRB实验室开发。该项目支持ROS 1/ROS 2多版本，同时提供Python命令行工具，可处理ROS1/ROS2格式的rosbag数据，适配多平台多场景的激光惯性里程计任务。

## 主要特性
1.  **无需传感器专属建模**：无需针对特定LiDAR/IMU做定制化参数调整
2.  **多平台兼容**：支持多种激光雷达、IMU组合，可在不同环境和硬件平台上运行
3.  **双部署方式**：提供PyPI Python包和ROS软件包，支持一键安装快速上手
4.  **灵活配置**：支持导出默认配置文件自定义参数，可手动指定IMU与LiDAR外参
5.  **自带可视化**：可选集成rerun-sdk实现里程计结果实时可视化
