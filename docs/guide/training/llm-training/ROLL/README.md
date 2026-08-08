# ROLL

ROLL 是阿里开源的大语言模型强化学习训练库，面向大规模 GPU 资源下的 RLHF、推理增强和多轮代理训练。

## 项目链接

- GitHub: <https://github.com/alibaba/ROLL>
- 项目主页: https://alibaba.github.io/ROLL/

## 项目概述

ROLL 全称 Reinforcement Learning Optimization for Large-Scale Learning，目标是在大模型后训练场景中提供高效、易用且可扩展的 RL 训练框架。它使用基于 Ray 的多角色分布式架构来调度训练、推理、采样和奖励计算，并集成 Megatron-Core、SGLang、vLLM 等组件，以支撑大语言模型在偏好对齐、复杂推理和多轮 agent 交互任务中的强化学习优化。

项目强调规模化和工程可用性，支持 FSDP2、Megatron、LoRA、异步训练、RLVR、Agentic Training 等能力，并围绕不同模型和算法提供示例配置。它适合需要在多机多卡环境中训练推理模型或工具调用代理的团队，也适合作为研究新型策略优化算法与大模型系统栈结合的实验平台。
