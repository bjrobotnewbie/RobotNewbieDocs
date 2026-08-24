# SGLATrack

基于相似度的层自适应视觉Transformer用于无人机跟踪（CVPR 2025）

## 项目链接

- GitHub: <https://github.com/GXNU-ZhongLab/SGLATrack>

## 项目概述

## 项目介绍
本项目是CVPR 2025论文《Similarity-Guided Layer-Adaptive Vision Transformer for UAV Tracking》的官方实现，名为SGLATrack，是一款面向无人机跟踪任务的视觉Transformer跟踪算法，同时也可适配通用视觉跟踪场景。项目提供了预训练模型与原始测试结果下载链接，支持在多个航拍与通用跟踪数据集上开展训练与测试。

## 主要特性
1.  **核心算法**：基于相似度引导的层自适应视觉Transformer架构，适配无人机跟踪场景
2.  **多版本支持**：提供基于DeiT、ViT、EVA三种不同主干网络的跟踪模型变体
3.  **性能优异**：在UAV123、UAVDT、DTB70等多个航拍数据集以及TrackingNet、LaSOT、GOT-10k等通用跟踪数据集上取得了领先的AUC、AO指标
4.  **完整流程**：提供了训练数据集与测试数据集的准备教程、项目路径配置方法，可快速部署复现实验结果
