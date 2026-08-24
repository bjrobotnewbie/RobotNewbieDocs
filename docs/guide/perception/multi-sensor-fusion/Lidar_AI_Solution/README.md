# Lidar_AI_Solution

一个展示激光雷达相关 AI 解决方案的项目，包括三个 GPU 加速的激光雷达/相机深度学习网络（PointPillars、CenterPoint、BEVFusion）以及相关库（cuPCL、3D 稀疏卷积、YUV2RGB、cuOSD）。

## 项目链接

- GitHub: <https://github.com/NVIDIA-AI-IOT/Lidar_AI_Solution>

## 项目概述

## 项目介绍
本项目是面向自动驾驶的激光雷达AI加速解决方案，基于GPU优化了3D稀疏卷积、CenterPoint、BEVFusion等多个激光雷达/相机深度学习网络及相关工具库，包括cuPCL、3D SparseConvolution、YUV2RGB、cuOSD等。项目支持快速部署各类激光雷达3D感知任务，可复现原生PyTorch实现的精度。

## 主要特性
1.  支持4款主流3D感知算法：PointPillars、CenterPoint、BEVFusion、V2XFusion，提供CUDA&TensorRT推理加速方案
2.  内置轻量化3D稀疏卷积推理引擎，支持INT8/FP16精度，内存占用低，精度损失小
3.  覆盖各算法完整流程：预处理、特征编码、融合解码、后处理，提供一键式推理、评估工具
4.  支持ONNX导出与PTQ/QAT量化方案，适配多类开源框架生态
5.  独立于部分第三方库，部署灵活性强，接口简洁易用
