# WLA

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/WLA/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[CoRL 2026] 统一世界建模、语言推理与动作合成的世界语言动作模型

## 项目链接

- GitHub: <https://github.com/SJTU-DENG-Lab/WLA>

## 项目介绍
本项目是被CoRL 2026收录的WLA（World-Language-Action Model），旨在实现统一的世界建模、语言推理与动作合成。项目提供了预训练模型权重、训练与评估代码，支持在LIBERO、RoboTwin 2.0、RMBench等机器人仿真与实机基准测试平台上使用，还支持从视频中学习新任务。

## 主要特性
1.  **核心能力**：实现多模态统一建模，可同时完成世界状态理解、自然语言推理和机器人动作生成
2.  **支持场景**：覆盖多类机器人任务基准，包括通用仿真套件与实机测试平台
3.  **灵活训练**：支持单任务、全任务套件训练，以及结合 unseen 任务视频的联合训练
4.  **已发布内容**：多场景预训练模型权重、主流基准的训练与评估代码、视频学习新任务代码
5.  **待发布内容**：高效模式、TTS模式相关代码
