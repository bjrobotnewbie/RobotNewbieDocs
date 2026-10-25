# MolmoBot

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/MolmoBot/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

MolmoB0T：大规模仿真实现零样本操作

## 项目链接

- GitHub: <https://github.com/allenai/MolmoBot>
- 项目主页: <https://allenai.github.io/MolmoBot>

## 项目介绍
MolmoBot 是论文《MolmoB0T: Large-Scale Simulation Enables Zero-Shot Manipulation》的配套代码与网站项目，主打基于大规模仿真实现零样本机械臂操作。该模型具备优秀的仿真到现实迁移能力，可适配多种全新场景、物体与相机视角，支持在DROID机器人平台上部署运行，仅需腕部相机和1个外部相机即可工作，且对相机摆放位置无严格要求。

## 主要特性
1.  **核心能力**：实现零样本机械臂操作，可泛化到未见过的场景、物体与相机视角
2.  **部署支持**：提供仿真交互演示与DROID实体机器人部署方案，兼容现有DROID、polymetis机器人搭建方案
3.  **配套资源**：开放数据集、预训练模型、代码与项目网站，支持研究者基于数据集进行训练实验，提供数据格式说明文档与批量下载工具。
