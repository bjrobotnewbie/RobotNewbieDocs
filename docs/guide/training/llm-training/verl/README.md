# verl

verl 是字节 Seed 团队发起的大语言模型强化学习后训练框架，源自 HybridFlow 论文并由社区维护。

## 项目链接

- GitHub: <https://github.com/verl-project/verl>
- 项目主页: https://verl.readthedocs.io/en/latest/index.html

## 项目概述

verl 面向 LLM 的高效、灵活、生产可用 RL 训练，核心是 HybridFlow 的 hybrid-controller 编程模型，用于描述和执行复杂后训练数据流。它支持 PPO、GRPO 等强化学习流程，并能与 FSDP、Megatron-LM、vLLM、SGLang、Hugging Face 模型等现有大模型基础设施集成。

该项目强调算法扩展、设备放置灵活性和训练/生成阶段之间的高效切换，适合构建大规模 RLHF、RLVR、推理模型训练和 agent 训练管线。verl 生态还衍生出 uni-agent、VeRL-Omni、vexact 等相关项目，覆盖统一代理框架、多模态/扩散模型后训练以及零 mismatch rollout 等方向。
