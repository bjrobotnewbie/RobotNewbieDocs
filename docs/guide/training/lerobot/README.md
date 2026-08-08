# LeRobot

## 资源简介

LeRobot 是由 Hugging Face 开发的开源机器人学习框架，旨在提供 PyTorch 版本的机器人模型、数据集和工具。官方目标为"降低_entry barrier，使每个人都能从共享数据集和预训练模型中受益"。

## 官方链接

* GitHub仓库：<https://github.com/huggingface/lerobot>
* 官方文档：<https://huggingface.co/docs/lerobot>
* HuggingFace主页：<https://huggingface.co/lerobot>

## 主要特点

* **硬件无关接口**：Python 原生接口，标准化控制，兼容从低成本机械臂（SO-100）到人形机器人的多种平台
* **标准化数据集格式**：LeRobotDataset 格式（Parquet + MP4/图像），支持 Hugging Face Hub 存储和流式传输
* **SOTA 模型库**：提供可直接迁移到真实机器人的前沿策略模型
* **开源生态支持**： democratize physical AI

## 支持的机器人平台

* **机械臂**：SO100、LeKiwi、Koch、HopeJR、OMX、EarthRover、Reachy2、OpenARM、Unitree G1
* **遥操作设备**：Gamepads、Keyboards、Phones

## 核心任务类型

* 模仿学习（ACT、Diffusion Policy、VQ-BeT、Multitask DiT Policy）
* 强化学习（HIL-SERL、TDMPC）
* 视觉-语言-动作（VLA）模型（Pi0Fast、Pi0.5、GR00T N1.5、SmolVLA、XVLA）

## 核心功能

* 统一 Robot 类接口，解耦控制逻辑与硬件
* LeRobotDataset 数据集格式，支持高效存储和流式传输
* 完整训练流程，支持多种策略模型
* 仿真和真实硬件评估
* Hugging Face Hub 集成
