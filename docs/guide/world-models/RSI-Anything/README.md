# RSI-Anything

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/RSI-Anything/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

RSI-Anything：利用世界模型解锁递归自我改进

## 项目链接

- GitHub: <https://github.com/Gen-Verse/RSI-Anything>
- 项目主页: <https://arxiv.org/abs/2610.13912>

## 项目介绍
RSI-Anything是一个基于JEPA-Anything构建的通用领域框架，核心是通过世界模型的预测与交互反馈实现递归自我改进。它遵循“提出→预测→选择→评估→学习→保留”的循环流程，将候选生成、预测引导选择、外部评估与学习整合为统一过程，已在代码修复、GUI交互、实验室规划、反应优化、免疫科学等多个领域验证应用。

## 主要特性
1. 通用领域适配：支持不同领域自定义状态、动作、预测目标与反馈，无需针对特定场景重构核心流程
2. 递归自我改进机制：通过多轮迭代，将交互经验转化为系统优化依据，持续提升决策与行动效果
3. 技术栈支撑：基于Python 3.10+，采用Apache-2.0开源协议，可对接Hugging Face相关数据集，具备学术研究与工程应用基础
