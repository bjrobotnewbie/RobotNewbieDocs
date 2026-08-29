# FMT-Firmware

Firmament 自动驾驶嵌入式系统

## 项目链接

- GitHub: <https://github.com/Firmament-Autopilot/FMT-Firmware>

## 项目介绍
FMT-Firmware是Firmament Autopilot的嵌入式自动驾驶系统，基于模型驱动设计(MBD)开发，可快速搭建无人机、无人车、无人船、机器人等自主移动载体的控制系统。
项目分为两部分：本仓库的嵌入式固件（C/C++编写，稳定高性能）和配套的FMT-Model仿真框架（基于MATLAB/Simulink，带算法库）。
它基于RT-Thread实时操作系统开发，支持跨平台编译，兼容Pixhawk FMUv2、FMUv5等多款开源飞控硬件，可通过Mavlink和QGroundcontrol进行通信。

## 主要特性
1.  采用模型驱动设计，开发效率高且易于调试，支持从Simulink模型自动生成适配多硬件平台的代码
2.  基于RT-Thread RTOS，实时性能优秀，社区活跃且集成大量第三方组件
3.  支持SIEON S1、AMOV ICF5、CUAV全系列多款飞控硬件
4.  支持Windows/Linux/Mac跨平台开发工具链
5.  配套完善的仿真与算法库生态，附带官方用户指南与硬件文档
