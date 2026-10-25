# BitVLA

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/BitVLA/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

BitVLA 官方实现：面向机器人操作的 1 位视觉 - 语言 - 动作模型

## 项目链接

- GitHub: <https://github.com/ustcwhy/BitVLA>

## 项目介绍
BitVLA是面向机器人操作任务的1-bit视觉语言动作模型，是该研究的官方实现，已被CoRL 2026收录。项目已开源预训练模型、论文、训练与评估代码，包含VLA微调代码与模型，预训练代码正在规划中。该模型可直接通过Hugging Face调用预训练权重，支持在LIBERO等机器人仿真数据集上完成机器人操作任务的视觉语言推理与动作生成。

## 主要特性
1.  **轻量化高效**：相比同级别模型内存占用更低，例如7.7B参数量的OpenVLA-OFT仅占用15.4GB显存
2.  **多任务适配**：支持视觉语言问答、机器人操作等多类任务，在LIBERO全子任务数据集上取得顶尖平均性能
3.  **灵活训练方案**：支持常规训练与OFT微调两种训练方式，提供完整的机器人预训练与评估流程
4.  **开箱即用**：已发布预训练模型，可直接部署使用
