# MoCapAct

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/datasets/MoCapAct/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

多任务仿真人类控制数据集

## 项目链接

- GitHub: <https://github.com/microsoft/MoCapAct>
- 项目主页: <https://microsoft.github.io/MoCapAct>

## 项目介绍
MoCapAct是一个用于仿真人形机器人控制的多任务数据集项目，基于运动捕捉（MoCap）片段实现，依托`dm_control`包的CMU人形机器人平台，提供了完整的代码库，支持从训练片段专家、收集专家rollouts构建数据集，到下游任务的策略蒸馏、强化学习（RL）及运动补全的全流程操作。项目数据集与模型已托管于Hugging Face平台，方便用户下载使用。

## 主要特性
1. 提供多类核心功能：训练片段专家、构建专家rollouts数据集、下载预训练专家与rollouts、策略蒸馏、下游任务RL训练、运动补全；
2. 数据集包含片段专家、多片段策略、迁移任务RL策略、GPT策略等模型，以及小型、大型两类rollouts数据集；
3. 支持基于运动捕捉片段学习人形机器人低阶运动技能，适配仿真人形机器人控制场景。
