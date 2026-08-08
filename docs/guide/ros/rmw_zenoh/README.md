# rmw_zenoh

基于Zenoh作为中间件实现的ROS 2 RMW

## 项目链接

- GitHub: <https://github.com/ros2/rmw_zenoh>

## 项目概述

## 项目介绍
这是一款基于Zenoh的ROS 2 RMW实现，通过zenoh-cpp绑定开发，将Zenoh作为ROS 2的中间件，用于实现ROS 2节点间的通信。支持通过二进制包或源码方式安装，适配多个ROS 2发行版。

## 主要特性
1.  基于Zenoh中间件的ROS 2通信实现，替代原生RMW中间件
2.  提供二进制安装与源码编译两种部署方式，二进制安装适合稳定开发，源码编译可获取最新特性
3.  支持自定义配置Zenoh编译参数，可选择使用系统预装的zenoh库或内置编译的依赖库
4.  适配主流ROS 2发行版，通过持续集成保障构建与代码风格合规性
