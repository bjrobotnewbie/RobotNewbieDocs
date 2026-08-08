# SuperSLAM

SuperSLAM：基于深度学习的视觉SLAM开源框架（开发中）

## 项目链接

- GitHub: <https://github.com/adityamwagh/SuperSLAM>

## 项目概述

## 项目介绍
SuperSLAM是一款基于深度学习的实时双目、RGB-D视觉SLAM开源框架（仍处于开发测试阶段，为Alpha版本）。它采用SuperPoint提取特征、LightGlue完成特征匹配，基于TensorRT FP16后端加速，以GTSAM作为优化核心，并支持位姿图回环检测。

## 主要特性
1.  支持实时运行，在NVIDIA RTX PRO 1000等硬件上可稳定超过相机帧率的追踪帧率
2.  在KITTI、EuRoC等主流视觉SLAM数据集上完成了精度测试，部分序列达到了极低的位姿误差
3.  采用深度学习特征匹配方案，适配复杂视觉场景
4.  支持双目视觉输入，可通过TensorRT实现前端加速

该框架可用于机器人定位导航、自主移动设备环境感知等场景。
