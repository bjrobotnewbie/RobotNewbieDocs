# evo

用于里程计与SLAM评估的Python包

## 项目链接

- GitHub: <https://github.com/MichaelGrupp/evo>
- 项目主页: https://michaelgrupp.github.io/evo/

## 项目概述

## 项目介绍
evo是一款用于评估里程计和SLAM算法的Python工具包，提供可执行程序与基础库，用于处理、评估和对比里程计与SLAM算法输出的轨迹数据。支持TUM轨迹文件、KITTI位姿文件、EuRoC MAV数据集格式，以及ROS/ROS2 bagfile中的多种话题消息格式。

## 主要特性
1.  支持多种主流轨迹数据集格式
2.  提供轨迹关联、对齐、单目SLAM尺度调整等算法工具
3.  支持灵活的绘图、可视化与导出（LaTeX图表、Excel表格等）
4.  拥有功能强大的可配置CLI工具，适配多数使用场景
5.  模块化的核心库与工具库，支持自定义扩展
6.  性能优于同类Python基准测试工具

可运行于Linux、macOS、Windows系统，兼容ROS与ROS2环境，最低要求Python 3.10+。
