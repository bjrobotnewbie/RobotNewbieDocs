# pi-zero-pytorch

物理智能提出的机器人基础模型架构π₀的实现

## 项目链接

- GitHub: <https://github.com/lucidrains/pi-zero-pytorch>

## 项目概述

## 项目介绍
本项目是Physical Intelligence提出的机器人基础模型架构π₀的PyTorch实现。该模型基于预训练视觉语言模型PaliGemma 2B构建，借鉴了Transfusion和Stable Diffusion 3的设计思路，采用流匹配替代扩散生成策略，并分离了联合注意力参数，用于机器人策略生成与在线强化学习。官方开源仓库已同步推出。

## 主要特性
1.  简化版Transfusion架构，适配机器人任务
2.  采用流匹配生成机器人策略，替代传统扩散模型
3.  支持基于PaliGemma 2B的多模态输入（视觉、指令、关节状态）
4.  内置EFPO类，可快速实现机器人在线强化学习
5.  依赖Einops、Flex Attention等工具优化张量管理与注意力混合计算

可通过pip快速安装，支持训练与采样流程，适用于机器人自主决策、多模态指令执行等场景。
