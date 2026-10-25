# orcs

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/orcs/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

训练特权型人形控制器的工具集

## 项目链接

- GitHub: <https://github.com/lok-i/orcs>

## 项目介绍
orcs全称Optimize, Retarget, Control Suite，是一款用于训练特权类人形控制器的工具包。它支持LoRA PEFT（目前适配SONIC）、SMPL运动的运动学动态重定向，以及从零开始训练（未经过充分测试）。项目提供了多种预设任务，包括全向移动、闪避、桌面操作等人形机器人控制场景。

## 主要特性
1.  支持LoRA参数高效微调，适配SONIC模型
2.  实现SMPL格式运动的动力学重定向
3.  内置多款人形机器人控制任务，涵盖行走、闪避、操作物体等场景
4.  支持Python 3.11环境，可通过uv或conda管理依赖，提供完整的开发和部署安装流程
