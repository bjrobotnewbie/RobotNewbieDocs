# OpenRLHF

基于 Ray 的易用、可扩展高性能智能体 RL 框架（支持PPO、DAPO、REINFORCE++、VLM、TIS、vLLM、Ray、异步 RL）

## 项目链接

- GitHub: <https://github.com/OpenRLHF/OpenRLHF>
- 项目主页: https://openrlhf.readthedocs.io/

## 项目概述

## 项目介绍
OpenRLHF是首个结合Ray + vLLM分布式架构与统一智能体设计范式的高性能、可用于生产环境的开源RLHF框架，支持基于人类反馈的可扩展强化学习。它内置了Molt后端，可支持千亿级参数模型的RL训练，同时保留简洁易用的工作流，还提供了完整的文档、技术报告与教程资源。

## 主要特性
1.  **分布式架构**：基于Ray、vLLM与DeepSpeed构建，支持高性能分布式训练
2.  **丰富RL算法**：支持PPO、REINFORCE++、GRPO、RLOO等主流强化学习算法，还包含DAPO、TIS等方案
3.  **统一智能体范式**：采用统一的智能体执行流水线设计，扩展性强
4.  **易用性**：轻量化且开箱即用，提供完整的RLHF全流程工具链，涵盖SFT、奖励模型训练与RL训练
5.  **超大模型支持**：借助Molt后端可训练千亿级参数的大模型
