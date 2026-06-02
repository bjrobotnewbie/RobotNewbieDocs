# DreamZero
首个开源世界动作模型（WAM），基于预训练视频扩散主干网络构建，实现了零样本物理泛化和跨机器人本体迁移。

## 核心特性
- 基于140亿参数自回归视频扩散模型构建
- 仅需10-20分钟数据即可完成跨机器人迁移
- 支持7Hz实时闭环控制
- 在未见任务上性能超过SOTA VLA模型2倍以上
- 支持纯视频演示、人类演示等多种数据来源

## 相关链接
- 📦 GitHub仓库：[https://github.com/dreamzero0/dreamzero](https://github.com/dreamzero0/dreamzero)
- 🤗 HuggingFace权重：
  - DreamZero-DROID: [https://huggingface.co/GEAR-Dreams/DreamZero-DROID](https://huggingface.co/GEAR-Dreams/DreamZero-DROID)
  - DreamZero-AgiBot: [https://huggingface.co/GEAR-Dreams/DreamZero-AgiBot](https://huggingface.co/GEAR-Dreams/DreamZero-AgiBot)
（注：访问需登录HuggingFace账号，权重本身公开可下载）
- 📄 论文：[World Action Models are Zero-shot Policies (arXiv:2602.15922)](https://arxiv.org/abs/2602.15922)
- 🏠 官方主页：[https://dreamzero0.github.io/](https://dreamzero0.github.io/)
