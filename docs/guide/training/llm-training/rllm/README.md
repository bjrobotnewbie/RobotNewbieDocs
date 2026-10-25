# rllm

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/llm-training/rllm/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

rLLM 是面向语言代理强化学习的开源框架，强调任意 harness、任意沙箱、任意训练后端的统一训练与评测流程。

## 项目链接

- GitHub: <https://github.com/rllm-org/rllm>
- 项目主页: https://docs.rllm-project.com

## 项目概述

rLLM 试图把 agent 评测与强化学习训练统一起来：同一段 agent 代码既可以用于 eval，也可以用于 rollout 和训练。它支持多种 CLI harness 和 Harbor 兼容任务目录，可以运行在 Docker、Daytona、Modal 或本地沙箱中，并可在 verl、tinker、Fireworks 等不同训练后端之间切换。

项目内置大量 benchmark，覆盖数学、代码、问答、搜索、视觉语言、翻译和 agentic 任务，并支持 GRPO、REINFORCE、RLOO、SFT、on-policy distillation 等训练方法。对于希望把现有代理、工具调用流程或 benchmark 快速接入 RL 训练的团队，rLLM 提供了较通用的封装方式和可复用的训练入口。
