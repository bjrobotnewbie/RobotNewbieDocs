# Relax

面向大规模全模态后训练的异步强化学习引擎

## 项目链接

- GitHub: <https://github.com/redai-infra/Relax>
- 项目主页: <https://redai-infra.github.io/Relax>

## 项目概述

## 项目介绍
Relax是小红书AI基础设施团队开源的高性能多模态大模型强化学习后训练框架，定位为大规模异步全模态RL训练引擎。它基于Ray Serve构建服务化架构，以Megatron-LM作为训练后端、SGLang作为推理引擎，通过TransferQueue实现训练与推理完全解耦，支持从文本到图像、视频、音频的端到端多模态RL训练。

## 主要特性
1.  **全模态训练支持**：统一支持文本、视觉、音频RL训练，是少数可完成Qwen3-Omni等全模态模型后训练的系统
2.  **服务化六层架构**：各模块均为独立Ray Serve部署，原生支持服务级弹性调度与故障恢复
3.  **异步流式训练**：通过TransferQueue实现Rollout、Actor等模块在独立GPU集群上运行，支持流式数据交换与可配置的延迟配置
4.  **混合部署模式**：支持Actor/Rollout分离部署搭配TransferQueue流式传输，其余模块可在Actor进程内运行，搭配数据平衡与子批推理减少GPU浪费
5.  **智能体RL能力**：支持多轮交互、损失掩码、灵活终止条件，实现闭环"执行→观察→决策"的VLM多模态上下文训练
