# YDLidar-SDK

接收 YD LiDAR 数据的驱动程序及更多功能

## 项目链接

- GitHub: <https://github.com/YDLIDAR/YDLidar-SDK>

## 项目介绍
YDLidar-SDK是面向所有YDLIDAR产品的软件开发工具包，基于C/C++开发，遵循YDLidar SDK通信协议，提供易用的C/C++、Python、C#风格API，支持在Linux、Windows系统运行，可快速连接YDLIDAR产品并获取激光扫描数据，适用于SLAM、机器人感知等需要激光雷达数据的场景。

## 主要特性
1. 支持多语言API：提供C/C++、Python（Windows仅支持Python2，Linux支持Python2/3）、C#接口，适配不同开发需求
2. 通信方式灵活：支持通过串口或网络连接激光雷达，可直接连接或通过适配器板连接
3. 跨平台兼容：支持Linux、Windows 7/10系统，要求C++11编译器
4. 协议开放：提供公开的通信协议，包含控制命令与数据格式，便于二次开发
5. 配套示例丰富：包含Linux/Windows示例、Python演示程序，降低开发门槛
