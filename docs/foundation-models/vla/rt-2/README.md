# RT-2
Google DeepMind 提出的VLA奠基性工作，首次将机器人动作表示为文本token，在互联网规模视觉语言数据上联合训练，开创了VLA这一研究方向。

## 核心特性
- 开创性工作：把机器人动作表示为文本tokens，和视觉语言token统一训练
- 从互联网数据迁移知识到机器人控制，具备 emergent 语义推理能力
- 能够从零样本执行复杂指令，比如"捡起最小尺寸的物体"
- 支持6-DoF机械臂控制，离散化动作空间，每个动作维度256个bins
- 在 unseen 任务上泛化能力比 RT-1 提升 2x+

## 相关链接
- 📦 GitHub仓库：[https://github.com/google-research/robotics_transformer](https://github.com/google-research/robotics_transformer)
- 📄 论文：[RT-2: Vision-Language-Action Models Transfer Web Knowledge to Robotic Control (arXiv:2307.15818)](https://arxiv.org/abs/2307.15818)
- 🏠 项目主页：[https://robotics-transformer2.github.io/](https://robotics-transformer2.github.io/)
