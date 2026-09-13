# RemoteIDReceiver

基于远程标识（Remote ID）技术的基于 WiFi 和蓝牙的无人机监控 Web 应用。

## 项目链接

- GitHub: <https://github.com/cyber-defence-campus/RemoteIDReceiver>

## 项目介绍
本项目是基于瑞士卢塞恩应用科学与艺术大学学士论文开发的无人机远程ID监控平台，可通过WiFi和蓝牙接收解析无人机远程ID广播信号，符合ASD-STAN prEN 4709-002标准，支持离线运行、实时监控与历史数据回放。
项目基于旧版Remote ID Receiver升级，提供模块化Python后端与VueJS前端，可捕获、解码、存储并可视化民用无人机的远程ID广播数据，当前仅支持WiFi信标传输，后续计划支持BLE和WiFi NaN传输方式。本项目仅为概念验证，不建议用于生产环境。

## 主要特性
1.  支持完整的ASD-STAN远程ID消息类型
2.  多线程高性能运行，提供REST+WebSocket双API接口
3.  内置可视化前端，支持自定义地图源（基于MapLibre JS）
4.  具备实时监控模式与历史数据回放模式，可离线部署地图服务
5.  支持离线运行，可存储无人机活动数据用于后续分析
