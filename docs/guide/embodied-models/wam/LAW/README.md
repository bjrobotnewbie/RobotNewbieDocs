# LAW

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/LAW/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

官方实现：论文"LAW：统一语言、动作与世界建模以增强智能体物理智能

## 项目链接

- GitHub: <https://github.com/hey-cjj/LAW>

## 项目介绍
LAW是论文《LAW: Unifying Language, Action, and World Modeling for Agentic Physical Intelligence》的官方实现，核心功能是将VLM规划、状态评估与价值估计和FastWAM或OpenWAM结合，提供RoboTwin的训练与推理 pipeline，用于智能体物理智能领域的研究。

## 主要特性
1. 支持Linux系统、Python 3.10及NVIDIA GPU，训练需4节点×8 GPU配置；
2. 提供LAW-FastWAM、LAW-VLM-FastWAM、LAW-OpenWAM、LAW-VLM-OpenWAM等公开模型，含Q1/Q2/Q3模块；
3. 配套提供WAM专家演示数据与VLM完整训练数据，可通过Hugging Face下载；
4. 适配RoboTwin环境、cuRobo及相关系统库，支持模型训练与全流程评估。
