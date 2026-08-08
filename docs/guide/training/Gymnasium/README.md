# Gymnasium

Gymnasium 是强化学习环境的标准 Python API 与参考环境集合，是 OpenAI Gym 的社区维护延续版本。

## 项目链接

- GitHub: <https://github.com/Farama-Foundation/Gymnasium>
- 项目主页: https://gymnasium.farama.org

## 项目概述

Gymnasium 为强化学习算法和环境之间提供统一接口，覆盖环境创建、重置、动作执行、奖励返回、终止状态和附加信息等核心交互流程。它内置经典控制、Box2D、Toy Text、MuJoCo、Atari 等环境族，并支持大量第三方环境按照同一 API 接入，因此常被用作强化学习算法开发、调试和基准比较的基础设施。

该项目由 Farama Foundation 维护，重点在于稳定 API、清晰文档和长期兼容生态。对于机器人学习和控制研究，Gymnasium 的价值在于提供统一的实验入口，使算法可以在简单离散任务、物理控制任务和更复杂模拟环境之间迁移测试，也方便与 CleanRL、PettingZoo 等相关库组成完整实验栈。
