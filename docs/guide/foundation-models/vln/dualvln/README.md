# DualVLN
DualVLN是首个双系统视觉语言导航基础模型，通过协同集成高层推理与低层动作执行，实现了出色的泛化能力和实时控制性能。

## 核心特性
- 双系统架构：VLM-based全局规划器(System 2) + 轻量级扩散策略(System 1)
- 全局规划器通过图像推理预测中期路径点
- 扩散策略实时生成平滑精确的轨迹
- 在所有VLN基准测试中取得SOTA性能
- 支持动态避障和复杂环境实时决策

## 相关链接
- 📦 GitHub仓库：[https://github.com/InternRobotics/InternNav](https://github.com/InternRobotics/InternNav)
- 📄 论文：[Ground Slow, Move Fast: A Dual-System Foundation Model for Generalizable Vision-Language Navigation (arXiv:2512.08186)](https://arxiv.org/abs/2512.08186)
- 🏠 官方主页：[https://dualvln.github.io/](https://dualvln.github.io/)
