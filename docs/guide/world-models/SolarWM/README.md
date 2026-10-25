# SolarWM

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/SolarWM/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

开放数据和可扩展的训练，用于长时程视频世界模型。

## 项目链接

- GitHub: <https://github.com/Junchao-cs/SolarWM>
- 项目主页: <https://junchao-cs.github.io/SolarWM-Web/>

## 项目介绍
SolarWM是一个开源的端到端长时序视频世界模型框架，覆盖数据准备、可扩展训练与长时序推理全流程。该项目提供了公开数据集与预训练模型权重，支持多机构联合研发，可用于构建多样化交互式视频世界模型。

## 主要特性
1.  **统一多模型支持**：单代码库兼容Wan2.2、LTX-2.5、MiniMax-H3共4款5B到33B参数的视频模型，共享数据、训练与推理接口，同时保留各主干网络原生特性与训练目标。
2.  **标准化三阶段训练流程**：采用双向适配、教师强制自回归初始化、分布匹配蒸馏的通用训练方案，适配异构视频主干网络。
3.  配套完整开源资源：提供公开数据集、模型权重、项目页面与学术论文，支持快速上手与二次开发。
