# representations4d

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/representations4d/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

4D 空间与时序视觉任务的基础模型。

## 项目链接

- GitHub: <https://github.com/google-deepmind/representations4d>

## 项目介绍
本项目是Google DeepMind推出的4D时空视觉任务基础模型仓库，聚焦通过自监督学习解决4D（3D空间+1D时间）视觉任务，涵盖相机位姿估计、点/目标跟踪、深度估计等非语义视觉任务。

## 主要特性
1.  **Scaling 4D Representations**：验证了基于Transformer视频模型的掩码自编码(MAE)可随模型规模从20M扩展到220亿参数，持续提升4D任务性能。
2.  **MooG**：提出可脱离固定像素网格的自监督视频表征方法，让隐层token随动态场景元素移动，通过跨注意力与位置嵌入解耦表征与图像结构，可学习以目标为中心的跟踪表征。
3.  **RVM**：基于循环Transformer的视频表征学习方法，通过非对称掩码目标与像素重建损失建模时间结构，在动作识别、跟踪、稠密几何任务上达到或超越SOTA，小模型场景下参数效率提升最高30倍。
4.  **Omnivorous DINO**：轻量级后训练方案，适配DINOv2等视觉基础模型，通过对齐多传感器视图特征，提升跨模态检索、场景理解能力与跨模态迁移性能。
