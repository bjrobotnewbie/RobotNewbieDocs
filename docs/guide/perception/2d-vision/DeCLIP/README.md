# DeCLIP

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/2d-vision/DeCLIP/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[CVPR 2025 / IEEE TPAMI 2026] DeCLIP: 解耦学习用于开放词汇密集感知

## 项目链接

- GitHub: <https://github.com/xiaomoguhz/DeCLIP>

## 项目介绍
DeCLIP是CVPR 2025收录的开源PyTorch实现项目，其扩展版本已被IEEE TPAMI接收。该项目是一种用于开放词汇密集感知的无监督微调框架，核心是通过解耦CLIP的自注意力模块，分离出“内容”与“上下文”特征，分别利用自监督学习和视觉基础模型进行训练，以提升局部特征的判别性与空间一致性。

## 主要特性
1. 针对CLIP在开放词汇密集预测中存在的图像令牌无法聚合空间或语义相关区域信息的问题，提出解耦特征增强策略；
2. 为开放词汇密集感知任务提供了简单有效的无监督微调方案；
3. 在多个开放词汇密集预测基准测试中，性能超越现有SOTA模型；
4. 已开源训练、推理及评估代码，支持与CAT-Seg等工具集成，适配Linux+Python 3.10.0+CUDA 11.7的运行环境。
