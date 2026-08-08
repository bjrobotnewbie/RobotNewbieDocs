# prime-rl

PRIME-RL 是 Prime Intellect 开源的大规模异步强化学习训练框架，面向多步 LLM agent 和 MoE 模型训练。

## 项目链接

- GitHub: <https://github.com/PrimeIntellect-ai/prime-rl>

## 项目概述

PRIME-RL 旨在提供易于修改但能扩展到超大规模 GPU 集群的 RL 训练框架。它支持完全异步的 agentic RL 训练流程，使用 FSDP2 进行训练、vLLM 进行推理，并结合 FP8 推理、PD disaggregation、专家并行和上下文并行等技术来提升大模型训练效率。

项目与 Verifiers 环境库和 Environments Hub 深度集成，可用于 SWE、工具调用、多轮代理和多模态任务的端到端后训练。它同时支持 SFT、RL 训练和评估，并提供 Slurm、Kubernetes、多节点部署和多种模型族适配，适合研究或工程团队探索 1000+ GPU 规模下的异步 agent 强化学习。
