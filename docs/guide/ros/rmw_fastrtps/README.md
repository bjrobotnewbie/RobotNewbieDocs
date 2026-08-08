# rmw_fastrtps

基于eProsima Fast RTPS的ROS Middleware（rmw）接口实现。

## 项目链接

- GitHub: <https://github.com/ros2/rmw_fastrtps>

## 项目概述

## 项目介绍
`rmw_fastrtps`是ROS 2的中间件实现，用于连接ROS 2与eProsima Fast DDS中间件，提供ROS中间层(RMW)接口。该实现已覆盖所有ROS 2发行版，可通过二进制包或源码获取。

## 主要特性
1.  提供两种Fast DDS适配实现：
    - `rmw_fastrtps_cpp`：默认实现，编译时生成消息类型映射
    - `rmw_fastrtps_dynamic_cpp`：运行时通过自省类型支持处理序列化/反序列化
2.  支持通过`RMW_IMPLEMENTATION`环境变量切换中间件实现
3.  内置默认Fast DDS配置：预分配可重分配内存策略、同步发布模式、关闭数据共享
4.  支持进阶自定义配置，包括修改发布模式、完整QoS配置、参与者发现选项、零拷贝数据共享、弱网大文件传输等场景。
