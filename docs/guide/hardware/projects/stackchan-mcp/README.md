# stackchan-mcp

StackChan (xiaozhi-esp32) MCP 网关：支持将任何 MCP 客户端与 CoreS3 + 伺服电机 + 相机机器人连接。

## 项目链接

- GitHub: <https://github.com/kisaragi-mochi/stackchan-mcp>

## 项目介绍
本项目是面向M5Stack官方StackChan（2025 Kickstarter发售套件）的MCP（Model Context Protocol）桥接工具，可以让任意LLM客户端驱动该机器人。项目基于stack-chan社区生态开发，通过Python网关实现MCP客户端与ESP32设备的通信，支持跨局域网远程访问，可替换原厂固件。

## 主要特性
1.  **核心功能**：支持通过Claude等MCP客户端调用StackChan的头部转动、相机拍照、触摸传感器读取、表情切换等操作
2.  **技术架构**：采用分层通信设计，LLM侧通过stdio MCP连接网关，网关通过WebSocket与ESP32通信，同时提供HTTP服务获取相机JPEG画面
3.  **支持硬件**：官方StackChan套件（基于CoreS3 ESP32-S3开发板，搭配双SCS0009舵机、GC0308相机等外设），兼容符合引脚配置的自制StackChan
4.  **项目结构**：为monorepo架构，包含适配StackChan的固件分支、Python网关程序、文档和示例代码
