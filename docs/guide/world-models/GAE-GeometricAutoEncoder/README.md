# GAE-GeometricAutoEncoder

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/GAE-GeometricAutoEncoder/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[arxiv'26] GAE：学习用于 3D 一致世界生成的几何原生潜在空间

## 项目链接

- GitHub: <https://github.com/TencentARC/GAE-GeometricAutoEncoder>

## 项目介绍
GAE（GeometricAutoEncoder）是一篇arXiv论文提出的几何自动编码器，核心是将3D归纳偏置融入生成状态本身，而非从外部向隐空间添加几何信息。它能将冻结的几何基础特征压缩为紧凑的单视图隐空间，解码后可同时输出RGB内容与几何信息，实现从共享隐空间生成相机控制的视频及3D几何结构。项目提供了公开代码，支持推理、训练、评估等功能，相关权重已在Hugging Face发布，配套有项目页面与演示视频。

## 主要特性
1. 内置3D归纳偏置，生成的隐空间具备原生几何特性，可同时输出RGB与几何信息
2. 采用双阶段架构，第一阶段为编解码器，冻结Depth Anything 3（DA3）基础特征
3. 提供完整CLI脚本，支持推理、训练、评估、数据处理等操作，配置文件可自定义运行方案
4. 配套有论文、项目页面、演示视频及Hugging Face权重，便于复现与应用
