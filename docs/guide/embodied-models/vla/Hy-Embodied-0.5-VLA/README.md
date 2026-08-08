# Hy-Embodied-0.5-VLA

从视觉-语言-动作模型到真实世界机器人学习栈

## 项目链接

- GitHub: <https://github.com/Tencent-Hunyuan/Hy-Embodied-0.5-VLA>

## 项目概述

## 项目介绍
本项目是腾讯 Robotics X 和 Hy 团队推出的 Hy-Embodied-0.5-VLA（简称 Hy-VLA），是一套端到端的视觉-语言-动作（VLA）机器人学习全栈方案，覆盖数据采集、模型设计、预训练、监督微调、RL后训练到真实部署全流程。项目提供了完整的代码库、两款预训练模型（Hy-Embodied-0.5-VLA-UMI、Hy-Embodied-0.5-VLA-RoboTwin）以及超2000小时的第一视角UMI数据集，支持在HuggingFace和ModelScope获取相关资源。

## 主要特性
1.  基于Hy-Embodied-0.5的MoT骨干网络，集成流匹配动作专家、多帧历史压缩记忆编码器以及与机器人本体运动解耦的delta-chunk动作表示
2.  支持RoboDojo基准测试，包含HDF5数据集加载器、训练与评估脚本以及策略适配器
3.  提供多平台的模型与数据集下载链接，适配真实机器人落地场景
