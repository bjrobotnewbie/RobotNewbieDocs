# Master Board
- GitHub仓库: https://github.com/open-dynamic-robot-initiative/master-board

## 项目概述
Master Board是Solo四足机器人的主控板硬件与固件项目，负责集中所有传感器和执行器的数据，并提供与实时计算机的有线和无线连接。该板支持多种通信方式：SPI接口可连接多达8个从设备，WiFi通过ESP-NOW实现无线通信（127字节消息往返时间约1.2ms），以太网有线通信（往返时间约0.2ms），以及GPIO和UART接口。固件基于ESP-IDF工具链开发，支持1kHz的无线闭环控制和以太网闭环控制，提供了多种状态LED指示，同时附带了详细的开发文档、固件烧录指南和SDK示例代码，是四足机器人项目的核心控制硬件方案。