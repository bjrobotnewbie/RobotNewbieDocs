# image_common

ROS中处理图像的通用代码

## 项目链接

- GitHub: <https://github.com/ros-perception/image_common>
- 项目主页: https://docs.ros.org/en/rolling/p/image_common/

## 项目概述

## 项目介绍
image_common是ROS 2机器人感知栈的一部分，提供了机器人系统中处理图像与相机的核心基础设施工具包。它包含多个子功能包，可用于图像传输、相机标定数据管理等场景，支持二进制和源码两种安装方式。

## 主要特性
1.  **image_transport**：核心图像传输库，采用插件式架构，支持raw、压缩等多种图像传输格式，无需修改应用代码即可切换传输方式，提供C++发布/订阅接口、消息过滤器集成、传输转换节点等功能，支持生命周期节点与QoS配置。
2.  **image_transport_py**：基于pybind11的Python绑定，将image_transport核心接口开放给Python3节点。
3.  **camera_calibration_parsers**：支持读写YAML、INI格式的`sensor_msgs/CameraInfo`标定数据，提供格式转换命令行工具。
4.  **camera_info_manager**：C++相机标定数据管理类，支持多协议加载标定文件、处理相机标定服务请求，线程安全且支持生命周期节点。
5.  **camera_info_manager_py**：纯Python版本的相机标定管理工具，兼容C++版本接口。
6.  配套提供官方教程，涵盖图像发布订阅、传输选择、自定义插件开发以及Python使用方法。
