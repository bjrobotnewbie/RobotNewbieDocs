# ViGAR

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/awesome-world-action-models/ViGAR/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

重新思考世界 - 动作模型：组合与上下文感知下的机器人操作

## 项目链接

- GitHub: <https://github.com/DAGroup-PKU/ViGAR>
- 项目主页: <https://dagroup-pku.github.io/ViGAR/>

## 项目介绍
ViGAR（Visual Goal-conditioned Action Reasoning）是一款面向组合式及上下文感知机器人操作的世界-动作模型，由北京大学、AgiBot、CocoMatrix联合研发。该项目旨在通过子任务分解与上下文学习，实现对未知长 horizon 机器人操作任务的高效处理，目前已在RoboTwin 2.0排行榜位列第3，支持仿真环境下的评估与训练，基于Python、PyTorch开发，采用MIT许可。

## 主要特性
1. 采用子目标规划器与世界-动作策略结合的架构，适配长 horizon 机器人操作任务
2. 支持组合式与上下文感知的机器人操作，可处理未知任务
3. 提供完整的仿真环境评估、训练代码及对应权重，支持RoboTwin平台
4. 具备任务多样性与长 horizon 数据训练能力，可实现子任务分解与上下文学习
