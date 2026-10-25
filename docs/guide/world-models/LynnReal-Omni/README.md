# LynnReal-Omni

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/LynnReal-Omni/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

LynnReal-Omni 将文本转视频、图像转视频、基于人体与手部姿态引导的生成、结构控制、全向参考生成、风格迁移、视频编辑、退化视频恢复以及长视频生成等能力整合到一个统一框架中，并支持四步快速生成。

## 项目链接

- GitHub: <https://github.com/LynnReal-AI/LynnReal-Omni>

## 项目介绍
LynnReal-Omni是一个多模态视频生成框架，支持文本转视频、图像转视频、人体/手部姿态引导生成、结构控制、全参考生成、风格迁移、视频编辑、低质量视频修复以及流式长视频生成，仅需4步即可快速完成生成。
该项目目前已支持ComfyUI，包含标准4步和Flash 3步两种工作流，单张H100显卡可在约8.4秒内生成一段带音频的1344×768分辨率视频。同时还推出了轻量化版本，可大幅降低显存和磁盘占用，且生成效果与原版本一致。本项目仍处于早期测试阶段，后续计划开源训练代码、部分训练数据以及更高效的DiT模型。

## 主要特性
1.  覆盖多类视频生成与编辑任务，包含文本/图像/姿态/参考图引导生成、风格迁移、视频修复等
2.  支持标准4步和Flash 3步两种极速生成流程，单H100可实现超短耗时产出
3.  提供轻量化 checkpoint 版本，降低50%以上的磁盘和显存占用，且生成效果无差异
4.  兼容ComfyUI，附带完整节点包和预设工作流，部署使用更便捷
