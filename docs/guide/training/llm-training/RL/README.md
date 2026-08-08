# RL

NeMo RL 是 NVIDIA NeMo 生态中的可扩展大模型后训练库，支持 SFT、DPO、GRPO、RLHF/RLVR 等训练流程。

## 项目链接

- GitHub: <https://github.com/NVIDIA-NeMo/RL>
- 项目主页: https://docs.nvidia.com/nemo/rl/latest/index.html

## 项目概述

NeMo RL 面向高效、可扩展的大语言模型和多模态模型后训练，结合 NVIDIA 的训练、推理和并行计算生态，支持 Megatron Core、DTensor/FSDP、vLLM、SGLang、LoRA、长上下文训练、异步 RL 等能力。项目提供面向 Nemotron、Qwen、GLM 等模型族的示例 recipe，并关注多节点 GPU 集群上的训练吞吐与工程稳定性。

该库适合需要在企业级 GPU 基础设施上复现或扩展大模型后训练流程的团队。它覆盖从监督微调、偏好优化到多奖励强化学习的多个阶段，也包含性能评测、配置示例和容器化发布，方便用户围绕推理增强、工具任务、代码任务或长上下文任务构建训练实验。
