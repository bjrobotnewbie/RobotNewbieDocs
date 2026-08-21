# verl-omni

多模态强化学习训练框架：扩散与全向模型

## 项目链接

- GitHub: <https://github.com/verl-project/verl-omni>
- 项目主页: <https://verl-omni.readthedocs.io/en/latest/index.html>

## 项目概述

## 项目介绍
VeRL-Omni是一款专注于多模态生成模型的强化学习（RL）训练框架，基于`verl`项目开发，旨在为扩散模型与全模态模型提供简单、快速且稳定的RL训练能力。它针对多模态生成类RL训练的特殊需求，提供专属的训练仓库以适配这类模型的结构、输入输出模式与计算特性。

## 主要特性
1.  **支持多类生成模型**：覆盖图像、视频、音频扩散模型（如Qwen-Image、Wan2.2）以及统一多模态理解生成模型（如BAGEL、HunyuanImage-3.0）的RL后训练。
2.  **集成多种先进算法**：支持FlowGRPO、GSPO、Flow-DPPO、DiffusionNFT、Diffusion DPO等定制化多模态RL训练算法，部分算法可跳过VAE解码直接对扩散隐空间评分，提升训练效率并降低资源消耗。
3.  **适配主流任务与模型**：已支持LTX2.3音视频生成、Qwen3-Omni、Wan2.2视频生成等任务，同时升级了vLLM-Omni推理后端以提升训练吞吐量。
4.  提供完整文档与社区支持，可通过官方文档、微信及Slack社区获取帮助。
