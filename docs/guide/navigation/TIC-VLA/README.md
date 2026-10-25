# TIC-VLA

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/TIC-VLA/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[ICML 2026] 思考 - 控制 (TIC)-VLA 用于机器人导航

## 项目链接

- GitHub: <https://github.com/ucla-mobility/TIC-VLA>

## 项目介绍
TIC-VLA是ICML 2026收录的延迟感知视觉-语言-动作模型，专为动态、以人为中心的机器人导航场景设计。本项目仓库提供模型代码、监督训练入口、DynaNav基准测试资源，以及基于IsaacLab的RL微调脚本，支持机器人在复杂动态环境下的导航任务。

## 主要特性
1. 核心模型：具备延迟感知能力的视觉-语言-动作模型，适配动态人机环境的导航需求
2. 配套资源：包含模型代码、训练配置、基准测试工具、RL微调脚本及相关数据集
3. 环境支持：基于Isaac Sim仿真平台，提供完整的环境搭建流程，支持conda训练环境与Isaac Sim仿真环境的分离配置
4. 训练体系：支持监督训练与RL微调，提供多阶段训练配置文件，可通过Hugging Face下载配套数据集与基础模型
