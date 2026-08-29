# BLEnky

快速配置的低功耗 BLE 到 GPIO 桥接器及 gpioASM 运行时

## 项目链接

- GitHub: <https://github.com/dakhnod/BLEnky>
- 项目主页: <https://ble.nullco.de>

## 项目介绍
BLEnky是一款面向nRF51/nRF52系列芯片的低功耗BLE到GPIO桥接固件，同时内置gpioASM运行时，可以快速将低成本蓝牙IO模块改造为智能外设，支持通过BLE控制LED、继电器、舵机、电机等输出设备，读取按键、传感器数据，还可搭建骑行传感器或HID控制器。
该固件可类比nRF平台的Tasmota，支持纽扣电池长期供电，用户可按需启用/关闭功能以节省RAM和Flash存储空间，支持多款官方和第三方nRF51/52开发板。

## 主要特性
1.  支持通过BLE读写芯片引脚，实现外设控制与数据采集
2.  可灵活裁剪功能以适配低存储需求场景
3.  兼容多款nRF51/nRF52开发板，包括nice!nano、XIAO nRF52840、nRF52840 Dongle等
4.  支持搭建骑行传感器、HID控制器等定制化蓝牙外设
5.  支持通过DFU方式快速烧录固件
