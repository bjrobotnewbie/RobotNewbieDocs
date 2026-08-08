# Agent-R1

Agent-R1 是用于端到端训练多步 LLM 代理的强化学习框架，把代理交互建模为逐步 MDP 轨迹。

## 项目链接

- GitHub: <https://github.com/AgentR1/Agent-R1>

## 项目概述

Agent-R1 面向需要工具使用、环境反馈和多轮决策的 LLM agent 训练。它不同于把完整交互历史拼成单个长序列的训练方式，而是把每一轮观察、动作、反馈、奖励和终止状态表示为 step-level MDP transition，从而让工具调用、上下文管理、奖励分配和策略优化成为统一训练基座的一部分。

项目提供分层抽象来解耦任务环境、rollout、奖励、优势估计和策略目标，并支持多种 agent 场景，例如网页/搜索、ALFWorld、WebShop、学术论文搜索以及视觉语言模型代理。它适合研究多步 LLM agent 强化学习、过程奖励、上下文截断/重写以及长时程工具交互训练的场景。
