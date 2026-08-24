# SLAM-Former

[ECCV 2026] SLAM-Former：将 SLAM 集成到统一 Transformer 架构

## 项目链接

- GitHub: <https://github.com/Tsinghua-MARS-Lab/SLAM-Former>
- 项目主页: <https://tsinghua-mars-lab.github.io/SLAM-Former/>

## 项目概述

## 项目介绍
SLAM-Former是清华大学MARS实验室推出的基于Transformer的端到端SLAM方案，被收录为ECCV 2026论文，目前已发布预印本。该项目将完整SLAM流程整合进单个Transformer模型中，支持基于图像序列的定位与建图任务，提供了完整的代码、预训练模型与部署教程。

## 主要特性
1.  **端到端Transformer SLAM**：将视觉SLAM的特征提取、位姿估计、建图全流程整合进单一Transformer架构
2.  **支持KV剪枝**：可通过调整`retention_ratio`参数平衡模型推理速度与精度
3.  **多版本预训练模型**：提供标准版与长序列优化版权重，支持不同分辨率输入，修复了网格伪影问题
4.  完整开源生态：包含推理、训练代码，配套数据集与详细部署指南，同时提供中文解读博客辅助理解
5.  支持自定义图像序列输入，可快速生成SLAM定位与建图结果
