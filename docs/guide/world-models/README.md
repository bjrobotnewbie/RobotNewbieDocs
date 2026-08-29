# 世界模型 (World Models)

世界模型是**具身智能的核心技术**之一，旨在让智能体学习环境的动态规律，从而实现未来预测、行为规划和决策。通过建模物理世界的变化规律，机器人可以在与环境交互前进行想象推演，大幅提高样本效率和规划质量。

## 分类说明

| 分类 | 主要内容 | 典型项目 |
|------|---------|---------|
| **NVIDIA Cosmos 生态** | 世界基础模型与物理AI平台 | Cosmos, Cosmos-Predict, Cosmos-Reason |
| **通用/机器人世界模型** | 物理世界动态预测 | DreamDojo, WoW, LeWM, RISE, Boundless |
| **自动驾驶世界模型** | BEV/交通场景预测 | BEVWorld, CarDreamer |
| **3D/虚拟世界模型** | 3D场景生成交互 | HunyuanWorld, LingBot-World |
| **代码/图像世界模型** | 程序状态/图像生成 | CWM, Sana |
| **资源汇总** | 世界模型研究资源 | Awesome-World-Models 等 |

## 项目列表

### NVIDIA Cosmos 世界模型生态

- [NVIDIA Cosmos](/guide/world-models/nvidia-cosmos/README) - 物理AI开发平台，世界基础模型用于物理世界模拟与预测
- [Cosmos](/guide/world-models/cosmos/README) - NVIDIA开放的全球模型、数据集和工具平台
- [Cosmos-Predict1](/guide/world-models/cosmos-predict1/README) - 通用物理AI世界基础模型集合，支持下游微调
- [Cosmos-Predict2.5](/guide/world-models/cosmos-predict2.5/README) - Cosmos世界基础模型2.5版本，2B/14B参数
- [Cosmos-Reason1](/guide/world-models/cosmos-reason1/README) - 7B推理视觉语言模型，物理常识理解与具身决策

### 通用/机器人世界模型

- [DreamDojo](/guide/world-models/dreamdojo/README) - NVIDIA基于4.4万小时人类视频预训练的通用机器人世界模型
- [WoW (World-Omniscient)](/guide/world-models/wow/README) - 多校联合物理一致生成式世界模型，200万机器人轨迹训练
- [LeWorldModel](/guide/world-models/leworldmodel/README) - Yann LeCun团队基于JEPA架构的轻量化端到端世界模型
- [RISE](/guide/world-models/RISE/README) - 组合世界模型+自改进机器人策略学习框架
- [Boundless World Model](/guide/world-models/boundless-world-model/README) - 面向具身智能的动作条件视频世界模拟器

### 自动驾驶世界模型

- [BEVWorld](/guide/world-models/bevworld/README) - 百度Apollo自动驾驶BEV多模态融合世界模型
- [CarDreamer](/guide/world-models/cardreamer/README) - 基于CARLA的自动驾驶世界模型学习研究平台

### 3D/虚拟世界模型

- [HunyuanWorld](/guide/world-models/hunyuanworld/README) - 腾讯原生3D世界生成模型，支持交互探索
- [LingBot-World](/guide/world-models/lingbot-world/README) - 蚂蚁实时交互3D环境世界模型，对标Genie 3

### 代码/图像世界模型

- [CWM (Code World Model)](/guide/world-models/cwm/README) - Meta代码世界模型，代码生成与程序状态推理
- [Sana](/guide/world-models/Sana/README) - NVIDIA高效高分辨率图像生成模型，含SANA-WM世界模型扩展

### 资源汇总

- [Awesome-World-Models](/guide/world-models/Awesome-World-Models/README) - 跨领域世界模型研究精选资源清单
- [Awesome-World-Model](/guide/world-models/Awesome-World-Model/README) - 自动驾驶世界模型论文收集清单
- [Awesome-Physics-Cognition-based-Video-Generation](/guide/world-models/Awesome-Physics-Cognition-based-Video-Generation/README) - 物理认知视频生成研究论文清单
- [awesome-3d-4d-world-models](/guide/world-models/awesome-3d-4d-world-models/README) - 3D/4D世界建模领域综述与资源
- [lingbot-video（面向具身智能的扩展型混合专家视频预训练）](/guide/world-models/lingbot-video/README)
- [AwesomeWorldModels（具身智能世界模型综合综述）](/guide/world-models/AwesomeWorldModels/README)
- [VAGEN（面向多轮VLM智能体的世界模型推理RL）](/guide/world-models/VAGEN/README)
- [cortex-mem（🧠 适用于OpenClaw、具身AI等自…）](/guide/world-models/cortex-mem/README)
- [INTACT-JEPA（INTACT: 无搜索的世界模型中的同构…）](/guide/world-models/INTACT-JEPA/README)
- [SuperMap（SuperMap 是具身人工智能的活态空…）](/guide/world-models/SuperMap/README)
- [Awesome-World-Models（世界模型定义综述：包含关于世界模型在通用…）](/guide/world-models/Awesome-World-Models/README)
- [stable-worldmodel（一个用于可复现的世界模型研究与评估的平台）](/guide/world-models/stable-worldmodel/README)
- [FastWAM（Fast-WAM 官方代码库：世界动作模…）](/guide/world-models/FastWAM/README)
- [OpenWorldLib（统一代码库以构建先进世界模型。）](/guide/world-models/OpenWorldLib/README)
- [AlayaWorld（全栈开源交互式长时世界模型。）](/guide/world-models/AlayaWorld/README)
- [Nucleoid（逻辑语言用于大语言模型 🌱🐋 构建世界模…）](/guide/world-models/Nucleoid/README)
- [Puffin（[ICLR 2026 & ArXiv 2…）](/guide/world-models/Puffin/README)
- [World-Simulator（[IEEE TPAMI 2026] 模拟…）](/guide/world-models/World-Simulator/README)
- [awesome-agentic-world-modeling（世界建模：基础、能力、定律与更多）](/guide/world-models/awesome-agentic-world-modeling/README)
- [HarnessEval-W（HarnessEval-W: 视觉世界的…）](/guide/world-models/HarnessEval-W/README)
- [Awesome-Interactive-World-Model（交互式视频世界模型的全面综述）](/guide/world-models/Awesome-Interactive-World-Model/README)
- [HelixWorld（🪐 HelixWorld: 实时交互式音…）](/guide/world-models/HelixWorld/README)
- [SimWAM（SimWAM：用于端到端自动驾驶的简单世…）](/guide/world-models/SimWAM/README)
- [wyrd-ecs-core（ECS 世界模型架构：实时数据 AI 框…）](/guide/world-models/wyrd-ecs-core/README)
- [HY-World-2.0（HY-World 2.0：用于重建、生成…）](/guide/world-models/HY-World-2.0/README)
- [Helios（Helios: 真实实时长视频生成模型）](/guide/world-models/Helios/README)
- [Awesome-Video-World-Models-with-AR-Diffusion（精选的超现实视频世界模型列表：涵盖算法、…）](/guide/world-models/Awesome-Video-World-Models-with-AR-Diffusion/README)
- [learn-world-model（掌握一切关于世界模型的知识）](/guide/world-models/learn-world-model/README)
- [Echo-Memory（Echo-Memory 官方代码：在条件…）](/guide/world-models/Echo-Memory/README)
- [N0-TWAM（N₀-TWAM: 一种基于触觉的世界动作…）](/guide/world-models/N0-TWAM/README)
- [ImageWAM（ImageWAM: 世界动作模型是否真的…）](/guide/world-models/ImageWAM/README)
- [NEWTON（NEWTON：具物理约束的视频生成代理规…）](/guide/world-models/NEWTON/README)
- [AWorld（轻松搜索、理解、复现并改进想法）](/guide/world-models/AWorld/README)
- [Causal-Forcing（[ICML 2026] "Causal …）](/guide/world-models/Causal-Forcing/README)
- [utopia（世界首个开源企业级世界模型。）](/guide/world-models/utopia/README)
- [LatentSpatialMemory（视频世界模型的潜在空间记忆）](/guide/world-models/LatentSpatialMemory/README)
- [awesome-world-action-models](/guide/world-models/awesome-world-action-models/README)
- [ForgeWM（使用 8 张 GPU 训练实时可玩的视频…）](/guide/world-models/ForgeWM/README)
