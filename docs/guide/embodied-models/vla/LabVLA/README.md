# LabVLA

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/LabVLA/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

LabVLA：面向科学实验室的视觉 - 语言 - 行动模型

## 项目链接

- GitHub: <https://github.com/zjunlp/LabVLA>
- 项目主页: <https://zjunlp.github.io/LabVLA/>

## 项目介绍
LabVLA是首个面向科学实验室的视觉-语言-动作基础模型，旨在打造能够实际执行科学实验的AI科学家。它基于Qwen3-VL-4B-Instruct视觉语言骨干模型，通过DiT流匹配动作专家将其转化为实时机器人控制器，采用FAST动作令牌预训练→带知识隔离的流匹配后训练→任务微调的π0.5训练流程。项目提供安装、训练与部署相关教程。

## 主要特性
1.  专为科学实验室场景设计的多模态大模型，打通视觉、语言与机器人动作控制链路
2.  基于Qwen3-VL-4B-Instruct构建，搭配定制化流匹配动作专家模块
3.  采用标准化π0.5训练流程保障模型效果
4.  提供完整的部署、训练与微调工具链

项目已开源代码、预训练模型，附带官方项目页面与arXiv论文供参考。
