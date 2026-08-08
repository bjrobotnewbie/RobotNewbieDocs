# asv-drones

适用于ArduPilot与PX4自动驾驶仪的地面站应用开源实现

## 项目链接

- GitHub: <https://github.com/asv-soft/asv-drones>

## 项目概述

## 项目介绍
asv-drones是一款面向ArduPilot和PX4自动驾驶仪的开源地面站应用，属于无人航空系统(UAS)领域的模块化开源平台，采用社区协作开发模式，旨在推动无人机领域的技术创新。

## 主要特性
1.  **模块化架构**：支持用户根据需求自定义功能模块，适配不同使用场景
2.  **完全开源**：全代码开源，支持用户二次开发与贡献迭代
3.  核心子模块：
    -  `Asv.Drones.Gbs`：地面基站服务模块，实现无人机与地面操控端的稳定通信
    -  `Asv.Gnss`：GNSS库，支持解析RTCMv2/RTCMv3/NMEA协议，可通过SBF/ComNav/UBX协议控制接收机
    -  `Asv.Mavlink`：适配.NET 9.0的MAVLink通信库，保障无人机通信符合标准协议
    -  `Asv.Common`：通用基础库，为全系列Asv类库提供通用类型与扩展方法
    -  另有已废弃的SDR载荷示例项目`Asv.Drones.Sdr`
