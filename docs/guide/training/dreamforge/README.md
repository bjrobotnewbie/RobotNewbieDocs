# dreamforge

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/dreamforge/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

将世界模型想象转化为机器人策略的修正训练数据——一个单卡的可验证管道（SmolVLA · LIBERO · CEM · 配对仿真回放）。

## 项目链接

- GitHub: <https://github.com/rzc156/dreamforge>
- 项目主页: <https://rzc156.github.io/dreamforge/>
- 中文文档: https://github.com/rzc156/dreamforge/blob/main/README_zh.md

## 项目介绍
dreamforge是一个单GPU端到端研究流水线，核心为可验证机制，将世界模型的想象转化为机器人策略的校正训练数据，用于解决机器人策略训练中离线世界模型评分无法预测决策质量的问题，通过挖掘策略自身失败状态、搜索校正动作块并经模拟器回放验证后，生成有效训练数据。

## 主要特性
1. 单GPU运行，支持RTX 5080等硬件，兼容Python 3.10+、PyTorch 2.x，适配LIBERO Spatial基准与SmolVLA-450M策略；
2. 具备可验证核心，所有想象动作需经真实模拟器回放验证后才用于训练；
3. 基于CEM方法搜索校正动作块，挖掘失败状态并生成配对模拟器回放数据；
4. 提供完整实验结果与可视化看板，支持测试与CI流程。
