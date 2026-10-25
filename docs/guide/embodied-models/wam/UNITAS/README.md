# UNITAS

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/UNITAS/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Unitas 官方代码库：一种面向具身操作的 3D 原生世界动作模型

## 项目链接

- GitHub: <https://github.com/DexForce/UNITAS>
- 项目主页: <https://unitas-wam.github.io/>

## 项目介绍
UNITAS是面向具身操作的3D原生世界动作模型，为该研究项目的官方代码库，相关论文已发布在arXiv，模型权重可在Hugging Face获取，数据集暂未上线，采用Apache 2.0许可。项目核心是在每次交互中，将观测、动作与场景动力学统一到共享的度量3D坐标系中，实现机器人与人类手部的通用表示。

## 主要特性
1. 采用单一物理空间，观测、动作与场景动力学共享度量3D世界坐标系；
2. 使用点轨迹作为通用运动表示，可同时表征机器人运动、人类手部运动及场景动力学；
3. 具备互补功能，支持机器人动作生成与动作条件下的场景预测。
