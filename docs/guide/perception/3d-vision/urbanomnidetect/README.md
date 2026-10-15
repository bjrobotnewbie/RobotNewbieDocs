# urbanomnidetect

一种无需标定即可泛化于 ego-车辆、基础设施及空中摄像机的单目 3D 关键点检测器，支持无标定 V2X 协同感知。

## 项目链接

- GitHub: <https://github.com/mkturkcan/urbanomnidetect>

## 项目介绍
urbanomnidetect是一款面向城市场景的无校准、跨视角单目3D目标检测工具，核心为基于单关键点的单目3D检测器，可适配自车、路侧、航拍等不同视角的相机，无需额外校准即可实现即插即用的V2X协同感知，相关成果发表于CVPR 2026 DriveX Workshop。

## 主要特性
1. 支持两类模型：UrbanOmniDetect-2（当前版本，具备COCO-80类目标检测、3D包围盒、跟踪、鸟瞰视图及离线轨迹优化功能）、UrbanOmniDetect（CVPR论文中的仅位姿模型）；
2. 适配多视角相机，无需校准即可跨视角通用；
3. 配套UrbanOmniView数据集，可支撑模型训练与验证；
4. 采用AGPL 3.0开源协议，提供预训练模型权重。
