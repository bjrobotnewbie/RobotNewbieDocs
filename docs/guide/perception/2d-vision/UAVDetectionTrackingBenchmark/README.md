# UAVDetectionTrackingBenchmark

## 项目链接

- GitHub: <https://github.com/KostadinovShalon/UAVDetectionTrackingBenchmark>

## 项目概述

## 项目介绍
本项目是为IROS 2021论文《基于深度神经网络的无人机视觉检测与跟踪：性能基准测试》搭建的基准测试仓库，包含相关代码、配置文件和数据集统计信息。项目使用OpenMMLab系列框架完成检测与跟踪任务，共用到MAV-VID、Drone-vs-Bird、Anti-UAV三个UAV相关数据集。

## 主要特性
1.  **核心功能**：提供UAV视觉检测与跟踪的基准测试代码与配置，支持基于深度神经网络的UAV检测跟踪性能评测
2.  **支持任务**：包含目标检测与多目标跟踪两个方向的测试流程
3.  **数据集覆盖**：适配MAV-VID、Drone-vs-Bird、Anti-UAV（含可见光与红外模态）三类公开UAV数据集
4.  **依赖环境**：基于PyTorch、OpenCV、MMCV、MMDet、MMTrack等主流计算机视觉框架开发
5.  **完整流程**：提供数据集转换、配置部署、模型测试的完整脚本与工具
