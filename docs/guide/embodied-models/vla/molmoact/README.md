# MolmoAct2
Allen Institute for AI 开源的全开放式VLA模型，首个完全开源（代码、权重、数据）且性能超越闭源模型，在LIBERO达到97.2%成功率。

## 核心特性
- 完全开源，包括代码、权重、训练配方均可复现
- 性能超越π0.5，性能媲美Gemini Robotics ER
- 每层KV连接机制，让动作生成器可以访问语言模型每一层输出，提升推理速度达到55.79Hz
- 自适应深度推理，提升空间理解能力
- 基于Flow Matching学习去噪动作，支持连续控制
- 在真实世界双操作达到87.1%成功率，成本低于$6000平台即可部署

## 相关链接
- 📦 GitHub仓库：[https://github.com/allenai/molmoact](https://github.com/allenai/molmoact)
- 🤗 HuggingFace权重：[https://huggingface.co/collections/allenai/molmoact-689697591a3936fba38174d](https://huggingface.co/collections/allenai/molmoact-689697591a3936fba38174d)
- 📄 论文：[MolmoAct2: The First Fully Open Robot Controller That Beats Closed-Source Giants (arXiv:2508.07917)](https://arxiv.org/abs/2508.07917)
- 🏠 官方博客：[https://mllog.dev/en/posts/molmoact2-action-reasoning-real-world-deployment/](https://mllog.dev/en/posts/molmoact2-action-reasoning-real-world-deployment/)
