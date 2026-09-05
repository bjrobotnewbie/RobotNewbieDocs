# Sky-Spy

无人机遥测数据检测与建图

## 项目链接

- GitHub: <https://github.com/colonelpanichacks/Sky-Spy>

## 项目介绍
Sky-Spy是OUI-SPY硬件平台的官方固件之一，用于检测并追踪通过WiFi和BLE广播RemoteID的无人机，可输出实时JSON数据供mesh-mapper.py可视化。它属于OUI-SPY固件生态，专注无人机RemoteID检测，可提取无人机的GPS坐标、高度、速度、航向等遥测数据，追踪操作员位置与无人机标识，支持多无人机跟踪。

## 主要特性
1.  针对OpenDroneID(ASTM F3411)协议优化，而非通用BLE设备扫描
2.  支持WiFi混杂模式扫描与BLE广播双协议探测
3.  输出标准JSON格式数据，适配mesh-mapper.py实时可视化
4.  支持多无人机跟踪，可提取并展示无人机标识、操作员位置与完整飞行遥测数据
5.  搭载独立FreeRTOS任务实现非阻塞蜂鸣音频告警
6.  适配官方OUI-SPY ESP32-S3开发板，同时兼容Seeed Studio XIAO ESP32-S3/C6开发板，支持外接无源蜂鸣器。
