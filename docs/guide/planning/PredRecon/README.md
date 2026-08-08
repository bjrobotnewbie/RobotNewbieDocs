# PredRecon

- 项目链接：https://github.com/HKUST-Aerial-Robotics/PredRecon

## 项目概述

PredRecon 是 ICRA'23 论文"PredRecon: A Prediction-boosted Planning Framework for Fast and High-quality Autonomous Aerial Reconstruction"的官方实现，提出了一种预测增强型规划框架，用于快速高质量自主空中重建。

PredRecon 是一个预测增强的规划框架，可以高效地对目标区域重建高质量 3D 模型。该方法由 HKUST 空中机器人组开发，结合预测模块和层次规划器，实现快速自主重建。

主要内容：
- 提供分层规划器代码
- 提供 AirSim 仿真环境
- 提供表面预测模块（SPM）代码
- 论文发表在 ICRA 2023

该框架通过预测boosting提升规划性能，使得无人机能够更快地完成自主 3D 重建，同时保持高质量重建结果。
