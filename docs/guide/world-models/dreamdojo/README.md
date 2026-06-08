# DreamDojo

DreamDojo: A Generalist Robot World Model from Large-Scale Human Videos

DreamDojo 是基于大规模人类视频预训练的通用机器人世界模型，由 NVIDIA Jim Fan 团队开发。该项目通过从大规模人类数据中获取全面的物理知识，使用潜在动作进行预训练，然后在目标具身系统上用连续机器人动作进行后训练，能够对多样化物体和环境展现出强大的泛化能力。

## 核心亮点

1. **大规模视频数据集**：4.4万小时多样化人类第一视角视频，是迄今为止用于世界模型预训练的最大规模数据集
2. **基础世界模型**：首个机器人世界模型，预训练后训练后能展现出对多样化物体和环境的强大泛化能力
3. **蒸馏流水线**：蒸馏后，模型可以实现长程自回归生成，以 10 FPS 的速度稳定实时交互超过 1 分钟

## 方法概述

DreamDojo 通过以下方式学习物理知识：
- 从大规模人类数据集中通过潜在动作预训练获取全面的物理知识
- 然后在目标具身系统上用连续机器人动作进行后训练
- DreamDojo-HV 数据集在规模和多样性上都表现出色，相比之前最大的世界模型训练数据集，包含 15 倍更长时长、96 倍更多技能、2000 倍更多场景

## 主要特性

- **物体和环境泛化**：能为 GR-1、G1、AgiBot、YAM 等不同机器人在各种环境和物体交互中生成逼真的动作条件 rollout
- **实时长程生成**：通过自回归几步蒸馏达到实时 10 FPS 生成，支持 1 分钟长程 rollout 评估
- **下游应用**：支持远程遥操作、策略评估、基于模型的规划等应用

## 项目信息

- **发布机构**：NVIDIA (Jim Fan 团队)
- **发布时间**：2026年2月
- **论文**：[https://arxiv.org/abs/2602.06949](https://arxiv.org/abs/2602.06949)
- **代码**：[https://github.com/NVIDIA/DreamDojo](https://github.com/NVIDIA/DreamDojo)
- **项目主页**：[https://dreamdojo-world.github.io/](https://dreamdojo-world.github.io/)
- **GitHub 仓库**：[https://github.com/NVIDIA/DreamDojo](https://github.com/NVIDIA/DreamDojo)

