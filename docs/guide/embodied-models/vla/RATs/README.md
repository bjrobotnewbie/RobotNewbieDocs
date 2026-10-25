# RATs

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/RATs/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

实现论文《Playful Agentic Robot Learning》

## 项目链接

- GitHub: <https://github.com/Playful-RATs/RATs>
- 项目主页: <https://playful-rats.github.io/>

## 项目介绍
RATs是CoRL 2026 Spotlight论文《Playful Agentic Robot Learning》的实现，是一种多智能体Code-as-Policy系统，用于机器人的终身技能学习。它通过LLM智能体在自由“玩耍”过程中自主生成任务、编写代码策略，并将成功执行的结果提炼为可复用的技能库；评估阶段直接复用这些技能作为规划器上下文，无需梯度计算或RL，仅通过结构化自然语言反馈和代码复用完成学习。

## 主要特性
1. 采用“提议者→规划者→策略编写者→验证者→故障诊断者”的循环，以好奇心驱动的方式获取技能，构建技能库；
2. 支持两种评估场景：在LIBERO-PRO、MolmoSpaces等域内环境中，以及在Robosuite、真实Franka Panda机器人上进行跨环境技能迁移；
3. 依赖uv管理Python 3.10环境，需CUDA-capable GPU运行，适配LIBERO-PRO等机器人任务环境。
