# OpenSplat

支持 CPU 和 GPU 的 Windows、Mac 和 Linux 平台生产级 3D 高斯泼溅

## 项目链接

- GitHub: <https://github.com/WebODM/OpenSplat>

## 项目介绍
OpenSplat是一款免费开源的3D高斯溅射（gaussian splatting）实现，采用C++编写，主打便携、轻量和高性能。它已加入WebODM生态，支持Windows、Mac、Linux系统，可通过CPU或GPU运行，GPU推荐NVIDIA、AMD及Apple Metal平台，CPU模式运行速度约慢100倍。

该工具可读取ODX、OpenSfM、COLMAP、OpenMVG或NerfStudio格式的相机位姿与稀疏点云数据，计算生成.ply、.splat、.spz或.rad格式的场景文件，可导入至其他软件中查看、编辑和渲染。

## 主要特性
1.  跨平台支持，兼容Windows、Mac、Linux系统
2.  支持CPU/GPU加速，GPU模式性能更佳
3.  支持多种主流三维重建项目格式的输入数据
4.  输出标准场景文件，可对接大量第三方3D高斯溅射软件生态
5.  提供预编译程序与源码编译两种部署方式
