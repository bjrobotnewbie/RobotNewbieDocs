# RoboHarness

一种机器人 harness，为 LLM 代理提供可视几何控制面板，使其能够直接理解并调用具身任务。

## 项目链接

- GitHub: <https://github.com/BinceQu/RoboHarness>
- 项目主页: <https://bincequ.github.io/RoboHarness/>
- 中文文档: https://github.com/bincequ/roboharness/blob/main/README.zh-CN.md

## 项目介绍
RoboHarness是一款为LLM智能体提供视觉几何控制面板的机器人工具，无需额外训练模型，通过视觉点击、关键点跟踪与几何约束的结合，让LLM智能体能够直接理解并执行具身任务。该项目适配BEHAVIOR仿真环境，支持Claude Code、Codex等多种LLM工具，可用于家庭操作类任务的具身控制与评估。

## 主要特性
1. 无需训练模型，直接为LLM智能体提供视觉几何控制能力，支持2D图像兴趣点标记与持续跟踪
2. 基于光流跟踪与深度反投影获取位置信息，生成精准基础动作完成复杂操作
3. 适配BEHAVIOR v3.9.1仿真环境，提供完整的任务定义、评估流程与参考结果
4. 支持多种LLM工具（Claude Code、Codex），可在Linux x86-64、NVIDIA RTX GPU、Python 3.11、CUDA 12.4环境下运行
