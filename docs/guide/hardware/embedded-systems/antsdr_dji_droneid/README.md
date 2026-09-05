# antsdr_dji_droneid

ANTSDR E200 DJI 无人机 ID 检测固件，集成网络接口

## 项目链接

- GitHub: <https://github.com/alphafox02/antsdr_dji_droneid>

## 项目介绍
本项目是基于ANTSDR E200 SDR的DJI无人机识别（DroneID）开源接收固件，可通过ZMQ协议输出识别数据，支持对接DroneID、DragonSync、Kismet、TAK/CoT等系统。支持识别O2/O3未加密协议和O4加密协议的DJI无人机，包括DJI Mini 5等新型号。

## 主要特性
1.  支持识别多协议DJI无人机：
    - O2/O3未加密机型：可获取序列号、机型、无人机/飞行员/返航点GPS、高度、速度、RSSI等数据
    - O4加密机型：可获取哈希ID、频率、RSSI，搭配DragonScope可解锁完整飞行数据
2.  兼容新旧版AntSDR固件，支持O4加密无人机检测
3.  提供网络接口集成方案，可快速配置设备网络参数，支持通过ZMQ向外输出识别数据
4.  附带详细的设备配置流程，支持通过串口完成固件初始化与网络设置
