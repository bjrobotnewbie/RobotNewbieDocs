# libpointmatcher

基于迭代最近点（ICP）算法的机器人 2D 与 3D 建图库

## 项目链接

- GitHub: <https://github.com/norlab-ulaval/libpointmatcher>
- 项目主页: <https://libpointmatcher.readthedocs.io/en/latest/>

## 项目介绍
libpointmatcher是一个模块化的C++点云配准库，实现了迭代最近点（ICP）算法，可用于机器人与计算机视觉领域的2D、3D建图，同时提供Python绑定。该项目被收录于多个优秀机器人、激光雷达相关开源项目列表中，支持Ubuntu 18.04/20.04/22.04，兼容x86、arm64/v8架构，据称也可在最新版Mac OS和Windows系统运行。

## 主要特性
1.  基于ICP算法实现点云精准配准
2.  采用C++编写以保证运行效率
3.  提供Python调用接口
4.  跨平台支持，适配多种操作系统与硬件架构
5.  模块化设计，便于扩展与定制
