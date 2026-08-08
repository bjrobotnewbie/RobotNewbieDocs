# MobileVLA-R1

[ECCV 2026] MobileVLA-R1：面向移动机器人的视觉-语言-动作强化

## 项目链接

- GitHub: <https://github.com/AIGeeksGroup/MobileVLA-R1>
- 项目主页: https://aigeeksgroup.github.io/MobileVLA-R1/

## 项目概述

## 项目介绍
MobileVLA-R1是ECCV 2026收录的四足机器人视觉语言动作（VLA）统一框架，旨在解决自然语言指令到四足机器人连续控制的落地难题。针对现有方法难以衔接高层语义推理与底层执行、泛化性不足的问题，该框架通过结构化思维链（CoT）对齐与GRPO强化学习实现显式推理与稳定连续控制。项目配套提供大规模多粒度CoT embodied轨迹数据集MobileVLA-CoT，以及两阶段训练范式：先监督CoT对齐，再结合GRPO强化推理一致性、控制稳定性与长时序执行能力。已在VLN、VLA任务中实现相较主流基线约5%的性能提升，并完成真实四足机器人部署验证。

## 主要特性
1.  统一四足机器人视觉语言动作框架，实现自然语言指令到连续控制的端到端落地
2.  构建大规模多粒度CoT轨迹数据集MobileVLA-CoT，提供结构化推理监督信号
3.  采用两阶段训练流程，结合监督对齐与GRPO强化学习优化模型性能
4.  真实场景部署验证，在复杂环境下展现优异鲁棒性
