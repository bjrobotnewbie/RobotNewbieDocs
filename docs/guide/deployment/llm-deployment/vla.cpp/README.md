# vla.cpp

VLA 模型统一推理运行时

## 项目链接

- GitHub: <https://github.com/VinRobotics/vla.cpp>
- 项目主页: <https://fai-modelopt-tech.github.io/vla-cpp.github.io/>

## 项目概述

## 项目介绍
vla.cpp是一个基于llama.cpp的C++视觉语言动作(VLA)模型统一推理运行时，支持运行SmolVLA、π0、BitVLA、Evo-1、GR00T等多款开源VLA策略模型，推理时无需Python和PyTorch，仅需单个自包含的GGUF格式模型文件。它可在CPU、Apple Silicon、CUDA显卡、Jetson开发板以及通过SYCL支持的Intel GPU上部署运行，适配从消费级硬件到边缘设备的多种平台。

## 主要特性
1.  统一支持多款主流开源VLA模型，无需针对不同模型单独适配
2.  轻量化部署，推理无额外Python/PyTorch依赖
3.  多硬件平台兼容，支持CPU、各类GPU及边缘设备
4.  基于llama.cpp构建，自动拉取依赖无需手动管理子模块
5.  提供完整文档说明引擎设计与各模型实现细节
