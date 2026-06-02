# XL-VLA (Cross-Hand Latent VLA)
UC San Diego 开源的灵巧操作VLA框架，CVPR 2026 论文，提出跨手潜在表示学习，实现灵巧操作跨 embodiment 泛化。

## 核心特性
- 跨手潜在空间共享，学习一个统一的潜在动作空间跨多种灵巧手
- 无监督潜在自编码器学习共享 latent action 编码
- VLA架构每个步预测一个潜在动作chunk，解码到具体机械手关节
- 大规模遥操作数据集包含~2M state-action pairs，覆盖4种不同灵巧手
- 零样本迁移到未见手-任务组合，性能优于原始关节空间基线

## 相关链接
- 📦 GitHub仓库：[https://github.com/EmptyBlueBox/DexLatent](https://github.com/EmptyBlueBox/DexLatent)
- 🤗 HuggingFace模型：[https://huggingface.co/GqJiang/XL-VLA](https://huggingface.co/GqJiang/XL-VLA)
- 📄 论文：[XL-VLA: Cross-Hand Latent Representation for Vision-Language-Action Models (arXiv:2603.10158)](https://arxiv.org/abs/2603.10158)
- 🏠 项目主页：[https://xl-vla.github.io/](https://xl-vla.github.io/)
