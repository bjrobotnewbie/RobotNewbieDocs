# vla-corrector

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/vla-corrector/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[NeurIPS 2026] VLA-Corrector: 轻量级检测与修正推理，支持自适应行动 horizon

## 项目链接

- GitHub: <https://github.com/ZJU-OmniAI/vla-corrector>
- 项目主页: <https://zju-omniai.github.io/vla-corrector/>

## 项目介绍
本项目为NeurIPS 2026收录的VLA-Corrector，是一款面向自适应动作 horizon 的轻量级检测-修正推理工具，由浙江大学与阿里巴巴达摩院联合开发，核心用于解决具身智能领域的VLA开环盲区问题，可实现机器人边执行任务边纠错。

## 主要特性
1. 采用轻量级设计，模型规模仅40M，推理效率高；
2. 具备检测-修正的核心能力，可针对VLA的动作偏差进行实时修正；
3. 适配具身智能相关场景，支持与ROS、SLAM、RL等技术结合使用。
