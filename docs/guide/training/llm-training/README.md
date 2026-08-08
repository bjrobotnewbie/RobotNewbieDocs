# 大模型训练

该分类收集大模型训练相关的框架和工具，涵盖 LLM 后训练、通用大模型训练和 LLM Agent 训练等领域。

## LLM 后训练

- [TRL（Transformers RL）](./trl/README) - HuggingFace 生态的 LLM 后训练库，支持 SFT、GRPO、DPO 等方法
- [Unsloth](./unsloth/README) - 高效 LLM 微调工具，支持 LoRA、4-bit 量化等
- [verl](./verl/README) - 字节跳动 Seed 团队的 LLM RL 后训练框架，支持 PPO、GRPO
- [XTuner](./xtuner/README) - InternLM 生态的大模型训练引擎，支持 MoE 模型高效训练
- [ROLL](./ROLL/README) - 阿里开源的 LLM RL 训练库，基于 Ray 分布式架构
- [NeMo RL](./RL/README) - NVIDIA 的可扩展大模型后训练库，集成 Megatron Core
- [PRIME-RL](./prime-rl/README) - Prime Intellect 的大规模异步 RL 训练框架，可扩展到 1000+ GPU
- [UniRL](./UniRL/README) - 腾讯混元统一多模态 RL 后训练框架，支持扩散模型和自回归模型

## 通用大模型训练

- [Flow-Factory](./Flow-Factory/README) - 用于扩散和流匹配模型的 RL 微调框架，支持多种模型和算法
- [LoongForge](./LoongForge/README) - 百度百舸开源的高性能统一训练框架，覆盖 LLM/VLM/扩散模型/具身智能模型训练

## LLM Agent 训练

- [ART（Agent Reinforcement Trainer）](./ART/README) - OpenPipe 的智能体 RL 训练框架，使用 GRPO 训练多步 LLM Agent
- [Agent-R1](./Agent-R1/README) - 端到端多步 LLM 代理 RL 训练框架，将交互建模为 MDP 轨迹
- [OpenEnv](./OpenEnv/README) - HuggingFace 的 Agent RL 训练隔离执行环境框架
- [verl-agent](./verl-agent/README) - 基于 verl 的 LLM/VLM Agent RL 扩展，支持多轮 rollout
- [rLLM](./rllm/README) - 语言代理 RL 训练框架，统一 agent 评测与 RL 训练流程
- [Verifiers](./verifiers/README) - LLM RL 环境构建与评估库，封装统一 RL 任务环境

- [trl（使用强化学习训练Transformer语…）](/guide/training/llm-training/trl/README)

- [ART（智能体强化训练器：使用GRPO为真实世界…）](/guide/training/llm-training/ART/README)

- [OpenRLHF（基于 Ray 的易用、可扩展高性能智能体…）](/guide/training/llm-training/OpenRLHF/README)

- [xtuner（面向超大规模MoE模型构建的下一代训练引…）](/guide/training/llm-training/xtuner/README)

- [ROLL（面向大语言模型强化学习的高效易用可扩展开…）](/guide/training/llm-training/ROLL/README)

- [OpenEnv（一个用于RL训练后与环境交互的接口库。）](/guide/training/llm-training/OpenEnv/README)

- [SkyRL（SkyRL: 面向大语言模型（LLMs）…）](/guide/training/llm-training/SkyRL/README)

- [prime-rl（大规模Agentic RL训练）](/guide/training/llm-training/prime-rl/README)

- [UniRL（UniRL是一个用于统一多模态模型强化学…）](/guide/training/llm-training/UniRL/README)

- [LoongForge（一个用于LLM、VLM、扩散模型和具身模…）](/guide/training/llm-training/LoongForge/README)

- [axrl（AxisRL 是一个基于 SGLang …）](/guide/training/llm-training/axrl/README)
