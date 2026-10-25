# WorldCrafter

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/WorldCrafter/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[Arxiv 2026] WorldCrafter: 具有隐式 3D 感知的视频世界模型

## 项目链接

- GitHub: <https://github.com/TencentARC/WorldCrafter>
- 项目主页: <https://drexubery.github.io/WorldCrafter/>

## 项目介绍
WorldCrafter是2026年Arxiv论文提出的视频世界模型，核心功能是基于图像或文本提示实现一致的、可相机控制的场景探索，通过相机可查询的隐式3D感知记忆，在不同视角和长时序下保留场景信息。项目提供WorldCrafter-Base和用于更快推理的蒸馏模型WorldCrafter-Fast，交互式演示代码和服务基础设施完全开源，支持社区运行、定制和二次开发。

## 主要特性
1. 具备隐式3D感知记忆能力，可跨视角、长时序保留场景信息，实现一致的场景探索
2. 提供两个模型版本：基础版WorldCrafter-Base、用于加速推理的蒸馏版WorldCrafter-Fast
3. 开源交互式演示代码与服务架构，支持社区自定义与扩展
4. 支持从图像或文本提示生成场景，可通过相机控制场景探索过程
