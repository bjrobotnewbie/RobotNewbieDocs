# llm-as-a-verifier

LLM-as-a-Verifier 是一个通用框架，可为任何代理提供细粒度的反馈，无需额外训练。它在编程、机器人和医疗代理基准测试中实现了最先进的性能。

## 项目链接

- GitHub: <https://github.com/llm-as-a-verifier/llm-as-a-verifier>
- 项目主页: <https://llm-as-a-verifier.com/docs/>

## 项目概述

## 项目介绍
LLM-as-a-Verifier是一个通用验证框架，无需额外训练即可为任意智能体提供细粒度反馈。它在编码、机器人、医疗智能体等多个基准测试中达到SOTA性能，支持多模态场景，可用于测试时优化、进度追踪和强化学习（RL）。

## 主要特性
1.  **核心能力**：通过细粒度评分粒度、基于LLM日志概率分布取期望、拆分评估标准与重复评估，生成精准反馈
2.  **性能表现**：在Terminal-Bench、SWE-Bench Verified、MedAgentBench、RoboRewardBench等智能体基准测试中取得SOTA结果
3.  **快速安装**：支持通过pip一键安装，也可从源码安装开发版
4.  **最新优化**：0.2.0版本新增前缀缓存优化（轨迹密集型基准测试减少约3.4倍未缓存输入令牌）、Terminal-Bench 2.1自验证基准、deepseek-v4-flash验证后端以及令牌用量统计功能
5.  **便捷使用**：提供`select`（候选方案择优）和`compare`（成对方案评分）等快速接口，支持多种LLM后端，兼容OpenAI格式API服务。
