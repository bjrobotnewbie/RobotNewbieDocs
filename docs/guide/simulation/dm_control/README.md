# dm_control

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/dm_control/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

- 项目链接：https://github.com/google-deepmind/dm_control

## 项目概述

dm_control 是 Google DeepMind 提供的基于物理模拟的基础设施，是使用 MuJoCo 物理引擎进行基于物理的模拟和强化学习环境的软件栈。

主要核心组件：
- `dm_control.mujoco`: 提供 MuJoCo 物理引擎的 Python 绑定
- `dm_control.suite`: 一组由 MuJoCo 物理引擎提供支持的 Python 强化学习环境
- `dm_control.viewer`: 交互式环境查看器

附加组件用于创建更复杂的控制任务：
- `dm_control.mjcf`: 在 Python 中编写和修改 MuJoCo MJCF 模型的库
- `dm_control.composer`: 从可重用、独立组件定义丰富 RL 环境的库
- `dm_control.locomotion`: 用于自定义任务的附加库
- `dm_control.locomotion.soccer`: 多智能体足球任务

该项目是强化学习和连续控制研究中广泛使用的基础设施，提供了 Colab 入门教程。
