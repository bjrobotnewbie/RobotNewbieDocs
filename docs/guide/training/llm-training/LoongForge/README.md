# LoongForge

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/llm-training/LoongForge/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

LoongForge 是百度百舸开源的高性能训练框架，覆盖 LLM、VLM、扩散模型和具身智能模型训练。

## 项目链接

- GitHub: <https://github.com/baidu-baige/LoongForge>
- 项目主页: https://baidu-baige.github.io/LoongForge/
- 中文文档: https://loongforge.readthedocs.io/zh-cn/latest/index.html

## 项目概述

LoongForge 是百度百舸 Loong 系列的一部分，定位为模块化、可扩展的统一训练框架，覆盖预训练、继续预训练和 SFT，并逐步扩展到 VLA、扩散模型和具身模型训练。它基于 Megatron-LM 做了系统级增强，重点优化模型覆盖、训练性能、硬件支持和大规模集群运行效率。

项目在开源前曾作为百度内部训练加速栈服务生产场景，README 中强调在企业客户和大规模 XPU/GPU 训练中的加速效果。它适合需要在 NVIDIA GPU、昆仑 XPU 等硬件上训练大模型或具身智能模型的团队，也为研究者提供了了解国产大模型训练工程实践、并行策略和硬件适配的入口。
