# rig_omni

开源 ESP32-S3 机器人固件，支持多种形态（Puppy 和 Hover）。功能包括语音 AI、EAF 情感动画、IMU 平衡控制、MCP 远程工具、OTA 更新以及 240×240 圆屏 LCD 显示。

## 项目链接

- GitHub: <https://github.com/LuwuDynamics/rig_omni>
- 项目主页: <https://luwudynamics.github.io/rig_omni/>
- 中文文档: https://github.com/luwudynamics/rig_omni/blob/main/README_CN.md

## 项目介绍
rig_omni是一款开源ESP32-S3机器人固件，支持四种机器人形态：五舵机机器狗Puppy、两轮平衡机器人Hover、机械臂ARM、以及《星际迷航》风格的带控制台的行走机器人TARS。该固件为机器人开发者提供直观、模块化的固件体验，支持本地离线唤醒词检测，对话识别与语音生成可调用网络服务，不同机器人形态共享语音交互、网络、传感器驱动及MCP工具，各形态具备专属运动控制与交互界面。

## 主要特性
- 语音AI：支持离线唤醒词、云端ASR/TTS、VAD、AGC功能
- 显示：圆形屏支持EAF表情，TARS配备专用双列控制台
- 运动控制：舵机步态、车轮平衡、Hover云台模式、机械臂校准与示教模式
- 连接性：BluFi WiFi配网、OTA固件更新、HMAC设备激活
- MCP工具：支持语音调用运动、校准、状态及TARS个性控制
- 其他：相机快照、BLE远程控制、Hover实时调试Web服务器、分板构建工具等
