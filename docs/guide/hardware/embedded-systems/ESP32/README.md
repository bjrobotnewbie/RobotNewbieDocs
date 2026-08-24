# ESP32

无人机桥接 ESP32。支持 WiFi 和 ESP-NOW 的加密及透明遥测链路，兼容 MAVLink、MSP、LTM 或任何其他协议。

## 项目链接

- GitHub: <https://github.com/DroneBridge/ESP32>
- 项目主页: <https://drone-bridge.com/>

## 项目概述

## 项目介绍
DroneBridge for ESP32是一款基于乐鑫ESP32模块的固件，是低成本的无人机/无人系统遥测通信方案。它可实现安全透明的串口转WiFi、串口转ESP-NOW、BLE链路，支持MAVLink、MSP、LTM等协议，也可配置为透明透传模式。仅支持低速率遥测通信，不支持视频编码传输。

## 主要特性
1.  支持双向链路：串口转WiFi、串口转远距离WiFi、串口转ESP-NOW、BLE
2.  兼容主流无人机地面站软件，如QGroundControl、Mission Planner等
3.  成本低廉，单模块仅约7元，重量小于8g
4.  标准WiFi模式下最远传输距离150m，ESP-NOW或WiFi LR模式下可达1km以上
5.  所有传输模式均采用AES-GCM 256位加密保障安全
6.  支持通过Web界面快速配置，可解析LTM、MSPv2、MAVLink协议并优化传输，还可向GCS注入RSSI信号
7.  另有针对无人机灯光秀优化的DLSE版本，支持Skybrush和远程电源管理
