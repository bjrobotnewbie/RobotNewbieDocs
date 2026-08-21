# 具身智能基础模型层 (Foundation Models for Embodied AI)

面向具身智能模型、VLA/VLM、机器人基础模型、多模态策略、语言条件控制、世界动作模型或大模型驱动机器人能力的项目。

## 模型集合

### [视觉语言动作模型（VLA）](/guide/embodied-models/vla/README)

直接将视觉输入和自然语言指令映射到机器人动作序列，是当前具身智能机器人的主流范式。包含 48 个开源 VLA 模型与框架。

### [世界动作模型（WAM）](/guide/embodied-models/wam/README)

世界动作模型通过预测未来世界状态来学习物理动力学，具备更强的泛化能力和物理直觉。包含 22 个开源 WAM 项目。

### [视觉语言导航模型（VLN）](/guide/embodied-models/vln/README)

让机器人根据自然语言指令在环境中自主导航到目标位置，是具身导航的核心任务。包含 6 个开源 VLN 模型。

## 机器人基础模型

- [Being-H](/guide/embodied-models/Being-H/README) - 人本化具身基础模型系列，含 WAM 模型（H0.7）和 VLA 模型（H0.5）

## 世界动作模型与评估

- [WorldArena](/guide/embodied-models/WorldArena/README) - 评估具身世界模型感知能力与功能效用的统一基准平台

## VLA 工具与评估

- [EmbodiedBench](/guide/embodied-models/EmbodiedBench/README) - 评估多模态大语言模型作为视觉驱动具身智能体的基准测试平台

## 资源与认知架构

- [Awesome-Embodied-Robotics-and-Agent](/guide/embodied-models/Awesome-Embodied-Robotics-and-Agent/README) - 精选研究列表，专注具身机器人及结合 VLM/LLM 的智能体领域
- [awesome-embodied-vla-va-vln](/guide/embodied-models/awesome-embodied-vla-va-vln/README) - 精选研究综述，聚焦 VLA、VLN 及多模态学习方法

## 分类说明

| 分类 | 核心思想 | 优势 |
|------|---------|------|
| **VLA** | (图像, 语言) -> 动作 直接映射 | 架构简洁，推理速度快 |
| **WAM** | 学习预测未来世界状态，泛化能力更强 | 具备物理直觉，零样本泛化能力强 |
| **VLN** | 语言导航，根据指令找到目标位置 | 长期导航任务，具身导航核心 |

- [awesome-spatial-intelligence（🌐 锻造空间智能：面向自主系统的多模态数…）](/guide/embodied-models/awesome-spatial-intelligence/README)

- [RoboCrew（🦾借助LLM智能体让你的机器人实现自主化…）](/guide/embodied-models/RoboCrew/README)

- [VLM-R1（使用强化VLM解决视觉理解问题）](/guide/embodied-models/VLM-R1/README)

- [Awesome-LLM-Robotics（一份将大语言/多模态模型用于机器人学/R…）](/guide/embodied-models/Awesome-LLM-Robotics/README)

- [rai（RAI 是一个面向物理人工智能机器人的厂…）](/guide/embodied-models/rai/README)

- [embodied-claude（为Claude赋予具身性的MCP集群）](/guide/embodied-models/embodied-claude/README)

- [Book-of-MLM（《多模态大模型：新一代人工智能技术范式》…）](/guide/embodied-models/Book-of-MLM/README)

- [minimal-embodiment（一个为大语言模型提供带有自我感知环路的闭…）](/guide/embodied-models/minimal-embodiment/README)

- [ScaleBFM（《Scaling Behavior Fo…）](/guide/embodied-models/ScaleBFM/README)

- [Vision-OPD（Vision-OPD 是一种区域到全球的…）](/guide/embodied-models/Vision-OPD/README)

- [Dispider（[CVPR 2025] Dispider…）](/guide/embodied-models/Dispider/README)

- [dive-into-embodied-ai（Build an embodied in…）](/guide/embodied-models/dive-into-embodied-ai/README)
