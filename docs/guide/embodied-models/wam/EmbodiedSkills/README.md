# EmbodiedSkills

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/EmbodiedSkills/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

RoboTwin 的模块化具身智能体运行时，集成了基于视觉语言模型（VLM）的语义 grounding、子目标调度、OpenPI/pi0.5 动作生成以及执行时验证。

## 项目链接

- GitHub: <https://github.com/ZJU4EmbodiedAI/EmbodiedSkills>
- 项目主页: <https://zju4embodiedai.github.io/EmbodiedSkills/>

## 项目介绍
EmbodiedSkills是面向RoboTwin的模块化具身智能体运行时，属于视觉-语言-动作（VLA）智能体框架，核心是通过世界动作模型（World Action Model）增强冻结的VLA策略，实现基于场景、语言指令和候选动作策略的预测决策，最终选择最优动作执行。其核心流程为五阶段级联技能反馈循环，可适配连续控制、空间操作等不同类型的策略，仅需微调后果模型与比较头，其余组件（动作策略、视觉骨干、语言编码器）保持冻结，降低适配成本。

## 主要特性
1. 模块化级联技能架构：分为Observe、Propose、Predict、Select、Execute五个阶段，通过可复用技能接口连接，支持不同类型策略参与同一反馈循环；
2. 预测决策机制：轻量级世界动作模型（WAM）预测候选动作的执行后果，结合多模型分歧与共识，通过比较头选择最优动作；
3. 高效适配：仅需微调后果模型与比较头，无需改动预训练的动作策略、视觉骨干和语言编码器；
4. 多组件集成：融合VLM grounding、子目标调度、OpenPI/pi0.5动作生成与执行时验证，适用于具身智能体的动作规划与执行场景。
