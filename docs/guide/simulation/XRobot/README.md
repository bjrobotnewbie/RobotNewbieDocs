# XRobot

XRobot 自动代码生成工具包

## 项目链接

- GitHub: <https://github.com/xrobot-org/XRobot>
- 项目主页: <https://xrobot.work/>

## 项目介绍
XRobot是一款颠覆传统的嵌入式软件开发框架，起源于Robomaster比赛，可适配裸机、RTOS、Linux以及Webots仿真等多种平台，兼顾开发效率、性能与内存占用。其最小仅需32k Flash+8k RAM即可运行完整demo，已在STM32系列MCU、树莓派等平台验证过实际运行效果，同时提供完善的官方文档与入门教程。

## 主要特性
1.  采用CMake、Clang、Ninja构建系统，支持跨平台高速编译
2.  支持VSCode/CLion一键编译调试与ClangTidy代码检查
3.  应用层全C++编写，代码复用率高，支持模块化即插即用开发
4.  兼容多开发板与操作系统，部分支持Arduino
5.  提供图形化/命令行参数配置、CLI界面与消息订阅发布功能
6.  内置CI/CD自动构建与固件发布流程，自带统一的系统API与通用工具组件
