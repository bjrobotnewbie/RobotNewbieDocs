# ViZDoom

ViZDoom 是基于 Doom 游戏引擎的视觉强化学习环境，用于训练仅依赖画面信息行动的 AI bot。

## 项目链接

- GitHub: <https://github.com/Farama-Foundation/ViZDoom>
- 项目主页: https://vizdoom.farama.org/

## 项目概述

ViZDoom 基于 ZDoom 引擎，将 Doom 游戏变成可编程的 AI 研究环境。它主要用于机器视觉学习和深度强化学习，智能体可以通过屏幕缓冲区、深度信息、对象标签、音频、游戏消息、地图几何等输入进行决策，并在自定义场景中学习导航、战斗、探索和目标完成策略。

项目提供 Python、C++ API，以及 Gymnasium/Gym wrapper，支持多平台运行、同步/异步单人和多人模式、自定义分辨率、离屏渲染、episode 录制和时间缩放等功能。它适合需要快速视觉 RL 环境、复杂第一人称决策任务或可脚本化 3D 游戏场景的研究者。
