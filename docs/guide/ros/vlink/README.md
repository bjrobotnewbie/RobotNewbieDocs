# vlink

VLink is a high-performance C++17 communication middleware for autonomous driving and embodied intelligence, positioned as a full-scenario alternative to ROS2.

## 项目链接

- GitHub: <https://github.com/thun-res/vlink>
- 项目主页: https://vlink.work

## 项目概述

## 项目介绍
VLink是面向自动驾驶与具身智能的高性能C++17通信中间件，定位为ROS2的全场景替代方案。它通过一套类型安全的统一API覆盖进程内、共享内存、车载以太网与跨机网络的全部通信需求，仅需修改URL前缀即可切换通信后端，无需改动业务代码。当前版本支持12种传输后端、14种序列化格式、3种通信模型与6个核心原语，还提供安全加密、录制回放、服务发现、10个CLI工具及Foxglove/Rerun可视化桥接能力，支持Linux、QNX、Android、macOS、Windows多平台。

## 主要特性
1.  **统一通信抽象**：以URL作为通信契约，通过scheme指定传输后端，业务代码与传输实现解耦，支持快速切换通信场景
2.  **三种通信模型**：
    - 事件发布/订阅：用于传感器数据、感知结果广播
    - 请求/响应方法：用于地图查询、参数读写等服务调用
    - 字段状态同步：用于车辆状态、配置参数同步
3.  多后端支持：覆盖进程内、共享内存、跨机网络等全场景通信需求
4.  丰富配套能力：提供安全加密、录制回放、服务发现、可视化桥接等工具链
