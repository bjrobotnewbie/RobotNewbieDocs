# verl-agent

verl-agent 是基于 veRL 的 LLM/VLM 代理强化学习扩展，面向长时程、多轮、可定制输入结构的 agent 训练。

## 项目链接

- GitHub: <https://github.com/langfengQ/verl-agent>
- 项目主页: https://huggingface.co/papers/2505.10978

## 项目概述

verl-agent 针对多轮 LLM agent 强化学习中的历史拼接、上下文增长和长任务训练问题，提出 step-independent multi-turn rollout 机制，使每一步输入结构、历史管理和记忆模块都可以灵活定制。项目也是 GiGPO（Group-in-Group Policy Optimization for LLM Agent Training）论文的官方实现，并在 veRL 基础上扩展了 agent 环境、算法和训练示例。

它支持文本和多模态代理、并行 Gym 环境、group-based RL、Qwen/Qwen-VL/LLaMA 等模型，以及多种长时程任务设置。对于研究 LLM/VLM agent 如何在 ALFWorld、Sokoban、搜索、视觉任务或多智能体任务中通过 RL 提升能力的用户，verl-agent 提供了较完整的算法和系统实现参考。
