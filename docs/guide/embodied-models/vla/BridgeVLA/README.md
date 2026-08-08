# BridgeVLA

✨✨ BridgeVLA 与 BridgeVLA++ 的官方实现

## 项目链接

- GitHub: <https://github.com/BridgeVLA/BridgeVLA>
- 项目主页: <https://bridgevla-plus.github.io/>

## 项目概述

## 项目介绍
BridgeVLA++是BridgeVLA的官方升级版，是一个数据高效、可泛化且带记忆增强的3D视觉语言动作（VLA）框架。它将输入输出对齐到共享的2D热力图空间，搭配统一的时空记忆模块来决策下一步动作与精准操作位置，支持双臂操作与新型机器人本体，同时也支持原版BridgeVLA（NeurIPS 2025）代码切换。
该项目提供了RLBench、COLOSSEUM、GemBench、MemoryBench、RMBench共5个仿真基准测试以及真实机器人部署的训练与评估代码，模型权重已上传至HuggingFace与ModelScope平台，在多个基准榜单上达到SOTA性能。

## 主要特性
1.  采用共享2D热力图空间对齐视觉语言输入与动作输出
2.  搭载统一时空记忆模块，实现动作与操作位置的精准决策
3.  支持双臂操作与多机器人本体适配
4.  数据高效，具备良好的任务泛化能力
5.  覆盖多类仿真测试与真实机器人部署场景
