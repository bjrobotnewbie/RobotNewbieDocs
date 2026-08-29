# EasyR1

EasyR1：一种基于 veRL 的多模态高效可扩展强化学习训练框架

## 项目链接

- GitHub: <https://github.com/hiyouga/EasyR1>
- 项目主页: <https://verl.readthedocs.io>

## 项目介绍
EasyR1是基于veRL开发的高效、可扩展多模态强化学习（RL）训练框架，为适配视觉语言模型进行了针对性优化，已被亚马逊云科技采用。它依托HybirdEngine设计与vLLM的SPMD模式实现高性能训练，支持通过Docker/Apptainer快速部署环境。

## 主要特性
1.  **支持模型**：Llama3、Qwen系列等语言模型，Qwen2-VL等视觉语言模型，以及DeepSeek-R1蒸馏模型
2.  **支持算法**：GRPO、DAPO、Reinforce++、ReMax、RLOO、GSPO、CISPO等RL训练算法
3.  **数据与训练技巧**：支持任意符合格式的文本、视觉文本数据集，提供无填充训练、LoRA训练、断点续训功能，支持Wandb、SwanLab等多平台训练追踪
4.  **部署便捷**：提供预构建Docker镜像与Dockerfile，支持从ModelScope下载模型
