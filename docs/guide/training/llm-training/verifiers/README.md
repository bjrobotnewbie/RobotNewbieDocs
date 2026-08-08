# verifiers

Verifiers 是面向大语言模型强化学习的环境构建与评估库，用于把任务、工具、沙箱和奖励函数组织成可训练的 RL 环境。

## 项目链接

- GitHub: <https://github.com/PrimeIntellect-ai/verifiers>

## 项目概述

Verifiers 关注 LLM 强化学习中的“环境”层：它把数据集、模型交互 harness、工具或沙箱、上下文管理和奖励/评分规则封装为统一任务环境，使同一套定义既可用于能力评估，也可用于生成训练轨迹和强化学习训练。项目与 Prime Intellect 的 Environments Hub、PRIME-RL 训练框架和托管训练平台有较紧密的配合，适合构建代码、搜索、浏览器、Lean、SWE 等多步代理任务。

相比只提供单次问答评分的评测脚本，Verifiers 更强调可复用的多轮环境抽象、rollout 记录、pass@k/ablation 等评估能力，以及与训练管线之间的衔接。它适合需要把自定义任务包装为 LLM agent 训练环境的研究者，也适合希望用统一方式评估不同模型、工具调用策略和代理框架的团队。
