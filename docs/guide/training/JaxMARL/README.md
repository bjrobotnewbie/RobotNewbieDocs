# JaxMARL

JaxMARL 是基于 JAX 的多智能体强化学习库，提供高效环境、常用基线算法和可向量化实验工具。

## 项目链接

- GitHub: <https://github.com/FLAIROx/JaxMARL>
- 项目主页: https://jaxmarl.foersterlab.com/

## 项目概述

JaxMARL 是一个面向多智能体强化学习（MARL）的 JAX 库，目标是在易用性和 GPU 加速效率之间取得平衡。项目提供多种常用 MARL 环境和基线算法，便于研究者在统一代码框架中评估不同方法，并利用 JAX 的向量化和编译能力提升实验吞吐。

README 中提到的环境覆盖 Overcooked、MPE、多智能体导航、Hanabi、Coin Game、SMAX 等任务，其中 SMAX 是对 StarCraft Multi-Agent Challenge 的向量化简化版本，避免运行完整 StarCraft II 引擎，降低大规模实验成本。项目还提供 Colab walkthrough、文档、安装说明和算法实现，适合快速上手。

JaxMARL 适合多智能体协作/竞争、通信、协同导航、离散策略学习和高效 benchmark 研究。对于需要大量并行实验或希望在 JAX 生态中复现 MARL 算法的用户，它提供了比传统 Python 环境更适合向量化训练的基础设施。