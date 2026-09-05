# 嵌入式系统

嵌入式系统是机器人硬件的控制核心，涵盖微控制器、嵌入式操作系统和外设驱动等内容。本章节聚焦机器人开发中常用的嵌入式平台和开发技能。

## 项目列表

- [51单片机入门](/guide/hardware/microcontroller-basics/README)
- [韦东山嵌入式Linux](/guide/hardware/embedded-linux/README)
- [野火STM32标准库](/guide/hardware/wildfire-stm32/README)
- [STM32主流工程](/guide/hardware/stm32-engineering/README)
- [STM32电机驱动](/guide/hardware/motor-control/README)
- [esphome（ESPHome 是一个通过简洁而强大的配…）](/guide/hardware/embedded-systems/esphome/README)
- [ethercat_driver_ros2（用于将EtherCAT模块与ros2_c…）](/guide/hardware/embedded-systems/ethercat_driver_ros2/README)
- [pycyphal（Cyphal 协议栈的 Python 实…）](/guide/hardware/embedded-systems/pycyphal/README)
- [mavlink（面向无人机的编组/通信库）](/guide/hardware/mavlink/README)
- [mavlink（面向无人机的编组/通信库）](/guide/hardware/embedded-systems/mavlink/README)
- [opendroneid-core-c（Open Drone ID 核心 C 库）](/guide/hardware/embedded-systems/opendroneid-core-c/README)
- [ESP32（无人机桥接 ESP32。支持 WiFi …）](/guide/hardware/embedded-systems/ESP32/README)
- [FMT-Firmware（Firmament 自动驾驶嵌入式系统）](/guide/hardware/embedded-systems/FMT-Firmware/README)
- [rosflight_firmware（ROSflight 自动飞控固件）](/guide/hardware/embedded-systems/rosflight_firmware/README)
- [BLEnky（快速配置的低功耗 BLE 到 GPIO …）](/guide/hardware/embedded-systems/BLEnky/README)
- [OpenExo（开源外骨骼）](/guide/hardware/embedded-systems/OpenExo/README)
- [Tasmota（适用于基于ESP8266和ESP32设备…）](/guide/hardware/embedded-systems/Tasmota/README)
- [WLED（通过ESP32基于WiFi控制WS281…）](/guide/hardware/embedded-systems/WLED/README)
- [antsdr_dji_droneid（ANTSDR E200 DJI 无人机 …）](/guide/hardware/embedded-systems/antsdr_dji_droneid/README)
## 分类说明

| 项目 | 主要内容 | 技能要点 |
|------|---------|---------|
| **51单片机入门** | 8051架构基础、外设驱动 | C语言编程、寄存器操作 |
| **韦东山嵌入式Linux** | Linux内核、驱动开发 | 设备树、内核模块、字符设备驱动 |
| **野火STM32标准库** | STM32标准库开发 | GPIO、UART、SPI、I2C、定时器 |
| **STM32主流工程** | STM32项目工程实践 | HAL库、FreeRTOS、通信协议 |
| **STM32电机驱动** | STM32电机控制实践 | PWM、编码器、PID控制 |

## 学习路径

```
51单片机入门 -> STM32标准库 -> STM32工程实践 -> 嵌入式Linux
```

建议从 51 单片机建立裸机开发概念，再过渡到 STM32 掌握常用外设和通信协议，最后学习嵌入式 Linux 进行复杂系统开发。
