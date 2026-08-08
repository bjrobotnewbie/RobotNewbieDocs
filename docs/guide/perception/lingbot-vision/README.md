# lingbot-vision

面向空间感知的自监督学习

## 项目链接

- GitHub: <https://github.com/Robbyant/lingbot-vision>

## 项目概述

## 项目介绍
LingBot-Vision是一系列面向稠密空间感知的自监督视觉Transformer（ViT）骨干网络，模型尺寸覆盖ViT-S/16到11亿参数的ViT-g/16。其旗舰模型采用**掩码边界建模**预训练目标，在学习空间结构化特征的同时保留强语义表征能力，可同时捕捉边界、形状与语义区域，作为即插即用的视觉编码器适配多种下游任务。

## 主要特性
1.  支持稠密空间感知相关下游任务：包括深度估计、语义分割、视频目标分割、深度补全（是LingBot-Depth 2.0的默认视觉编码器）以及稠密特征可视化
2.  采用边界-centric的自监督预训练目标，兼顾几何结构与语义表征
3.  提供多尺寸模型可选，已在HuggingFace、ModelScope开源，遵循Apache-2.0开源协议
4.  LingBot-Depth 2.0基于该编码器升级，在1.5亿样本RGB-D数据集上取得了远超前代方案的性能表现
