# OMG

官方仓库： "OMG: 通用多模态运动生成与通用 humanoid 控制"，https://arxiv.org/abs/2606.10340

## 项目链接

- GitHub: <https://github.com/Tsinghua-MARS-Lab/OMG>
- 项目主页: <https://tsinghua-mars-lab.github.io/OMG/>

## 项目概述

## 项目介绍
本项目是论文《OMG: Omni-Modal Motion Generation for Generalist Humanoid Control》的官方代码仓库，针对通用人形机器人控制打造全模态运动生成模型。项目提供了论文预印本、官方数据集、预训练模型，曾获RSS 2026的ExWBC口头报告与RoboData spotlight奖项。

## 主要特性
1.  **核心功能**：基于扩散模型实现全模态输入的人形机器人运动生成，支持端到端的训练、推理与部署流程，可适配G1人形机器人。
2.  **配套资源**：发布了LeRobotDataset v3格式的OMG-Data数据集，提供50M/100M/300M/500M多个参数量级的预训练模型 checkpoint 与评估工具。
3.  **使用场景**：适用于人形机器人通用运动控制研发，可快速生成适配不同任务的机器人运动轨迹，支持快速部署到实体机器人进行测试。
4.  **便捷部署**：提供一键式环境安装脚本，支持国内网络优化安装流程，同时支持TensorRT/CUDA加速推理。
