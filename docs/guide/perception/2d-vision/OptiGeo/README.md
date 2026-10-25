# OptiGeo

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/2d-vision/OptiGeo/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[CORL2026] 论文官方实现：《OptiGeo：光环境下的具身感知高效单目几何》

## 项目链接

- GitHub: <https://github.com/mx-liu6/OptiGeo>
- 项目主页: <https://mx-liu6.github.io/OptiGeo-web/>

## 项目介绍
OptiGeo是CORL 2026论文的官方实现，针对光学恶劣场景下的具身感知任务，提出高效单目几何解决方案，将透明、反光物体的深度估计重构为单目几何训练中的局部偏差校正任务。项目面向弱光、反光、透明物体等光学干扰场景，解决具身智能中的感知难题，已开源论文、项目页、模型权重、推理/训练代码及配置文件。

## 主要特性
1.  采用干净几何教师网络与残差对齐方式，修正带偏的真实深度监督信号
2.  仅含30M参数量的轻量模型，可在光学恶劣场景下实现精准高效的具身感知
3.  配套提供Hugging Face模型权重、完整推理与训练流程代码，支持快速部署与复现
