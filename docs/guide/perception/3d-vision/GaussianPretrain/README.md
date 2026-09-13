# GaussianPretrain

GaussianPretrain 用于自动驾驶的视觉预训练，展示了在多种 3D 感知任务中的显著改进，包括 3D 目标检测、高地图构建和占用预测。

## 项目链接

- GitHub: <https://github.com/Public-BOTs/GaussianPretrain>

## 项目介绍
GaussianPretrain是首个将3D Gaussian Splatting技术应用于自动驾驶视觉预训练的项目，针对自动驾驶场景下的3D感知任务设计。项目基于MMDetection3D开发，可实现3D目标检测、高精地图构建、占用预测等任务，在保证效率和更低内存占用的前提下，取得了显著的性能提升。

## 主要特性
1.  首次将3D Gaussian Splatting融入视觉预训练任务，兼顾效果与鲁棒性
2.  支持多视图图像输入，通过LiDAR深度引导生成有效掩码补丁与可学习3D高斯锚点
3.  可基于RGB、深度、占用重建信号解码高斯锚点参数
4.  已在多个3D感知任务上实现SOTA性能，支持结合LiDAR模态进一步提升效果
5.  完整代码与预训练权重已公开，提供UVTR-CS配置与模型权重下载
