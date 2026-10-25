# Olaf-World

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/Olaf-World/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[ICML 2026] 面向视频世界建模的潜在动作定向

## 项目链接

- GitHub: <https://github.com/showlab/Olaf-World>
- 项目主页: <https://showlab.github.io/Olaf-World/>

## 项目介绍
Olaf-World是ICML 2026收录的视频世界建模项目，核心是基于定向潜在动作（LAM）实现视频世界建模，支持零样本动作迁移，可将参考视频的动作（作为潜在动作序列）迁移至目标首帧，无需微调。目前已发布LAM的训练、推理代码及预训练权重，相关代码仓库、项目页面及HuggingFace模型均已开放。

## 主要特性
1. 核心技术：采用定向潜在动作（LAM）方法，结合视频世界建模技术；
2. 零样本动作迁移：无需微调，可将参考视频的动作迁移至目标首帧；
3. 训练与评估：基于MiraData、MIND数据集开展LAM及世界模型的预训练、微调与评估，训练包含SeqΔ-REPA、自强制蒸馏等流程；
4. 易用性：提供快速上手的推理脚本，支持通过HuggingFace下载预训练权重，配置流程简洁。
