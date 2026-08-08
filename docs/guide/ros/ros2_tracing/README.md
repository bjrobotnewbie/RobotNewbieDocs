# ros2_tracing

ROS 2 追踪工具

## 项目链接

- GitHub: <https://github.com/ros2/ros2_tracing>
- 项目主页: <https://docs.ros.org/en/rolling/>

## 项目概述

## 项目介绍
`ros2_tracing`是一款面向ROS 2的追踪工具套件，为核心ROS 2包提供追踪 instrumentation，同时支持通过Launch动作配置追踪，以及`ros2` CLI追踪命令。目前仅支持Linux系统，依赖LTTng追踪器，需根据ROS 2发行版选择对应分支使用。

## 主要特性
1.  为ROS 2核心组件提供追踪埋点能力
2.  支持通过Launch文件和CLI命令配置追踪流程
3.  低开销实时追踪框架，可用于分析分布式ROS 2系统的消息流转
4.  已有学术论文支撑，可用于机器人系统性能优化、算法改进等场景
