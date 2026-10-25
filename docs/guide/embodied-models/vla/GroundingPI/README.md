# GroundingPI

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/GroundingPI/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

面向物理智能的 4B 级基础模型。统一了检测、指代、指向、OCR、GUI 及布局定位任务，在 34 个基准测试中达到 SOTA 整体水平，并在受控评估中提升了机器人的泛化能力和数据效率。

## 项目链接

- GitHub: <https://github.com/groundingpi/GroundingPI>
- 项目主页: <https://groundingpi.github.io/>

## 项目介绍
GroundingPI是一款面向物理智能的4B参数 grounding 基础模型，核心围绕视觉基元构建，旨在为机器人领域提供视觉与物理交互的支撑能力。

## 主要特性
1. 功能覆盖全面，统一支持检测、指称、指向、OCR、GUI、布局 grounding 等多类视觉任务；
2. 在34个基准测试中取得SOTA整体性能，可提升机器人的泛化能力与数据效率；
3. 支持vLLM、Transformers后端部署，提供OpenAI兼容API，还具备批量标注（JSONL格式）能力，可通过Hugging Face、ModelScope等平台获取模型与Demo。
