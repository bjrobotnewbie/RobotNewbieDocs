# rosbridge_suite

rosbridge v2 协议的服务端实现

## 项目链接

- GitHub: <https://github.com/RobotWebTools/rosbridge_suite>
- 项目主页: https://robotwebtools.github.io

## 项目概述

## 项目介绍
rosbridge_suite是rosbridge v2协议的服务器端实现套件，为ROS提供JSON接口，支持任意客户端通过JSON格式数据发布/订阅ROS话题、调用ROS服务等操作，支持WebSocket、TCP多种传输层。它属于Robot Web Tools项目组，兼容ROS Humble、Jazzy、Rolling版本，整体为ROS元包集合。

套件包含多个核心子包：`rosbridge_library`提供处理JSON字符串、控制ROS发布订阅/服务调用的Python API；`rosbridge_server`实现WebSocket服务器以暴露`rosbridge_library`能力；`rosapi`提供获取ROS元信息、操作参数服务器的服务调用接口。

同时支持多语言客户端，包括JavaScript的roslibjs、Java的jrosbridge、Python的roslibpy、Rust的roslibrust等。

## 主要特性
1.  实现rosbridge v2协议，提供标准化JSON格式的ROS交互接口
2.  支持WebSocket、TCP多种传输层
3.  覆盖话题收发、服务调用、参数服务器操作等完整ROS交互能力
4.  多语言客户端生态支持，适配不同开发场景
5.  遵循BSD开源协议，质量等级为ROS Quality Level 3
