# MuscleMimic

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/musclemimic/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

- GitHub仓库: https://github.com/amathislab/musclemimic
- 项目主页: https://arxiv.org/abs/2603.25544

## 项目概述
MuscleMimic是一个基于JAX的运动模仿学习研究基准测试平台，专为生物力学精确的肌肉驱动模型设计。它专注于通过高性能神经策略训练推进肌肉驱动的运动和操纵研究，解决了在复杂生物力学模型上训练神经策略的计算挑战。其核心特性包括：肌肉驱动动力学支持（基于Hill型动力学的生理精确肌肉模型）、JAX/MJWarp加速（GPU并行训练，支持多达8192个环境以快速实验）、单一通用策略（在多样化数据集上训练的集中式策略，实现多种步态和运动的高维协调）以及AMASS集成（自动重定向SMPL格式运动数据集）。
- [Uni-SuperMimic（SuperMimic-UniLab：基于…）](/guide/training/musclemimic/Uni-SuperMimic/README)
