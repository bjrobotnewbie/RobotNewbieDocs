# Motus2

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/Motus2/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Motus2: 一种自我演化的灵巧操作通用世界模型

## 项目链接

- GitHub: <https://github.com/shengshu-ai/Motus2>

## 项目介绍
Motus2是一款面向灵巧操作的自进化通用世界模型，旨在构建统一的具身智能系统，实现感知、预测、动作、评估与改进的闭环流程。该模型通过模型缩放与数据缩放两大方向推进世界建模技术，适配仿生机器人平台，支持灵巧操作任务的自主优化。

## 主要特性
1. 采用共享权重的单模型架构，提供策略（世界-动作模型）、模拟器（动作条件世界模型）、评估器（价值模型）三类控制接口，形成闭环决策学习循环，利用专家演示与失败/次优交互数据优化策略。
2. 数据规模逐步扩展，从大规模单目自我中心数据，到同步双目自我中心数据，再结合机器人轨迹与人机对齐数据完成机器人领域适配。
3. 支持滑动窗口上下文的全局自回归与混合内存扩展，集成触觉反馈实现接触感知控制，已在具备双目视觉、双臂、双灵巧手及触觉传感的全仿生平台上验证。
4. 计划于2026年9月逐步发布代码与预训练检查点，涵盖视频预训练、视频-动作（价值）训练、模型基强化学习（MBRL）等相关代码。
