# AlphaBrain

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/AlphaBrain/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

综合体智能模型工具集

## 项目链接

- GitHub: <https://github.com/AlphaBrainGroup/AlphaBrain>

## 项目介绍
AlphaBrain是面向具身智能研究的模块化开源工具包，为开发者提供开箱即用的全功能具身智能研究框架，统一整合多种视觉语言动作（VLA）架构、世界模型主干、生物启发学习算法及强化学习（RL）范式，降低具身智能研究的使用门槛。

## 主要特性
1. 生物启发VLA（NeuroVLA）：首个开源生物启发VLA模型，在生物启发控制任务上达SOTA，结合脉冲神经网络（SNN）与STDP学习规则。
2. 跨架构持续学习：首个针对跨架构VLA的开源持续学习算法，突破架构兼容瓶颈，支持不同VLA模型间的通用适配与知识积累。
3. RLT_a训练范式：首个基于RL Token的开源VLA训练架构，通过信息瓶颈压缩VLA隐藏状态，结合离策略Actor-Critic强化学习。
4. 原生世界模型集成：首个原生集成Cosmos Policy原始权重的开源VLA，支持Cosmos 2/2.5、Wan 2.2、V-JEPA 2.1等世界模型的灵活切换。
5. 综合基准测试套件：适配最新具身基准，开源支持LIBERO、LIBERO-plus、RoboCasa、RoboCasa365等长时任务执行与记忆相关测试。
