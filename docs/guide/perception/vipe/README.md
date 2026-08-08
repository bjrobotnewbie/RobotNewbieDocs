# ViPE

- 项目链接：https://github.com/nv-tlabs/vipe
- 项目主页：https://research.nvidia.com/labs/toronto-ai/vipe

## 项目概述

ViPE（Video Pose Engine）是NVIDIA开发的**用于几何3D感知的视频姿态估计引擎**，这是一个实用的开源空间AI工具，能够从原始视频中标注相机姿态和稠密深度图。主要功能包括：

1. **完整估计**：从不约束的原始视频中估计相机内参、相机运动和稠密近度量深度图
2. **支持多种相机**：支持针孔相机、广角相机和360度全景视频
3. **持续优化**：最新1.2.0版本通过CUDA融合内核等优化实现了2.7倍加速且不损失精度
4. **生态集成**：支持Depth-Anything 3、Lyra等流水线，可通过PyPI直接安装使用

ViPE为从视频中获取3D几何信息提供了便捷高效的工具，降低了3D感知研究的数据标注门槛。