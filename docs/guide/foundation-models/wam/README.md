# 世界动作模型

世界动作模型（WAM）是具身智能的下一代范式，区别于直接将视觉语言输入映射到动作的VLA模型，WAM通过预测未来世界状态来学习物理动力学，具备更强的泛化能力和物理直觉。

## 目录

- [DreamZero](/guide/foundation-models/wam/dreamzero/README.md)
- [Cosmos Policy](/guide/foundation-models/wam/cosmos-policy/README.md)
- [UnifoLM-WMA-0](/guide/foundation-models/wam/unifolwm/README.md)
- [Awesome-WAM](/guide/foundation-models/wam/awesome-wam/README.md)
- [TesserAct](/guide/foundation-models/wam/tesseract/README.md)
- [Large Video Planner](/guide/foundation-models/wam/lvp/README.md)
- [4DGen](/guide/foundation-models/wam/4dgen/README.md)
- [LaPA](/guide/foundation-models/wam/lapa/README.md)
- [mimic-video](/guide/foundation-models/wam/mimic-video/README.md)
- [villa-X](/guide/foundation-models/wam/villa-x/README.md)
- [WorldVLA](/guide/foundation-models/wam/worldvla/README.md)
- [RynnVLA-002](/guide/foundation-models/wam/rynnvla-002/README.md)
- [GigaWorld-Policy](/guide/foundation-models/wam/gigaworld-policy/README.md)
- [FRAPPE](/guide/foundation-models/wam/frappe/README.md)
- [Motus](/guide/foundation-models/wam/motus/README.md)
- [Diffusion Reward](/guide/foundation-models/wam/diffusion-reward/README.md)
- [SRPO](/guide/foundation-models/wam/srpo/README.md)
- [WoVR](/guide/foundation-models/wam/wovr/README.md)
- [Interactive World Simulator](/guide/foundation-models/wam/interactive-world-sim/README.md)


## 什么是世界动作模型(WAM)

与VLA模型不同，WAM通过预测未来世界状态（视频）和动作来学习物理动力学，利用视频作为世界演化的密集表征。这种"世界模型+逆动力学"的架构，让模型首次实现了**零样本物理泛化**，对新任务和新环境的泛化能力提升超过2倍。

## 核心优势

1. **物理直觉**：显式建模世界动态，具备对物理规律的理解
2. **少样本迁移**：仅需10-30分钟数据即可迁移到新机器人或新任务
3. **实时控制**：14B参数模型可实现7Hz实时闭环控制
4. **跨模态泛化**：支持纯视频演示、人类演示等多种数据来源

## 开源项目

### DreamZero

DreamZero是首个开源的世界动作模型，由NVIDIA GEAR实验室开发，实现了零样本物理泛化和跨机器人本体迁移。

详细信息：[DreamZero](/guide/foundation-models/wam/dreamzero/README.md)

### Cosmos Policy

NVIDIA 开源的世界动作模型，专为通用机器人设计，在LIBERO基准测试中达到82.2%成功率。

详细信息：[Cosmos Policy](/guide/foundation-models/wam/cosmos-policy/README.md)

### UnifoLM-WMA-0

宇树科技开源的世界模型动作框架（WMA），为具身智能机器人提供仿真引擎和策略增强的完整解决方案。

详细信息：[UnifoLM-WMA-0](/guide/foundation-models/wam/unifolwm/README.md)

### Awesome-WAM

复旦大学开源整理的世界动作模型(WAM)研究综述，系统梳理了WAM领域的最新进展和分类。

详细信息：[Awesome-WAM](/guide/foundation-models/wam/awesome-wam/README.md)

### TesserAct

TesserAct: 学习4D具身世界模型，ICCV 2025。学习4D空间时间维度的环境动态，基于显式世界建模提升泛化能力。

详细信息：[TesserAct](/guide/foundation-models/wam/tesseract/README.md)

### Large Video Planner (LV-P)

Large Video Planner: 大型视频规划器框架，实现通用机器人控制，基于视频生成模型进行长程规划。

详细信息：[Large Video Planner](/guide/foundation-models/wam/lvp/README.md)

### 4DGen

Geometry-aware 4D Video Generation for Robot Manipulation, ICLR 2026。几何感知的4D视频生成，专为机器人操作设计。

详细信息：[4DGen](/guide/foundation-models/wam/4dgen/README.md)

### LaPA

Latent Action Pretraining from Videos, ICLR 2025。从视频中进行潜在动作预训练，无需交互数据。

详细信息：[LaPA](/guide/foundation-models/wam/lapa/README.md)

### mimic-video

mimic-video: Video-Action Models for Generalizable Robot Control Beyond VLAs, arXiv 2025。视频动作模型框架，超越传统VLA实现更好泛化。

详细信息：[mimic-video](/guide/foundation-models/wam/mimic-video/README.md)

### villa-X

villa-X: Enhancing Latent Action Modeling in Vision-Language-Action Models, ICLR 2026。增强视觉语言动作模型中的潜在动作建模。

详细信息：[villa-X](/guide/foundation-models/wam/villa-x/README.md)

### WorldVLA

WorldVLA: Towards Autoregressive Action World Model, arXiv 2025。阿里巴巴达摩院开源，自回归动作世界模型框架。

详细信息：[WorldVLA](/guide/foundation-models/wam/worldvla/README.md)

### RynnVLA-002

RynnVLA-002: A Unified Vision-Language-Action and World Model, arXiv 2025。阿里巴巴达摩院开源，统一的视觉语言动作和世界模型。

详细信息：[RynnVLA-002](/guide/foundation-models/wam/rynnvla-002/README.md)

### GigaWorld-Policy

GigaWorld-Policy: An Efficient Action-Centered World-Action Model, arXiv 2026。高效的以动作中心的世界动作模型。

详细信息：[GigaWorld-Policy](/guide/foundation-models/wam/gigaworld-policy/README.md)

### FRAPPE

FRAPPE: Infusing World Modeling into Generalist Policies via Multiple Future Representation Alignment, arXiv 2026。通过多未来表示对齐将世界建模注入通用策略。

详细信息：[FRAPPE](/guide/foundation-models/wam/frappe/README.md)

### Motus

Motus: A Unified Latent Action World Model, arXiv 2025。清华团队开源，统一的潜在动作世界模型框架。

详细信息：[Motus](/guide/foundation-models/wam/motus/README.md)

### Diffusion Reward

Diffusion Reward: Learning Rewards via Conditional Video Diffusion, ECCV 2024。通过条件视频扩散学习奖励函数。

详细信息：[Diffusion Reward](/guide/foundation-models/wam/diffusion-reward/README.md)

### SRPO

SRPO: Self-Referential Policy Optimization for Vision-Language-Action Models, arXiv 2025。视觉语言动作模型的自引用策略优化。

详细信息：[SRPO](/guide/foundation-models/wam/srpo/README.md)

### WoVR

WoVR: World Models as Reliable Simulators for Post-Training VLA Policies with RL, arXiv 2026。将世界模型作为可靠模拟器用于VLA策略后训练。

详细信息：[WoVR](/guide/foundation-models/wam/wovr/README.md)

### Interactive World Simulator

Interactive World Simulator for Robot Policy Training and Evaluation, arXiv 2026。交互式世界模拟器，用于机器人策略训练和评估。

详细信息：[Interactive World Simulator](/guide/foundation-models/wam/interactive-world-sim/README.md)
