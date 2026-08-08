# RynnBrain

RynnBrain：开放具身基础模型

## 项目链接

- GitHub: <https://github.com/alibaba-damo-academy/RynnBrain>

## 项目概述

## 项目介绍
RynnBrain是阿里巴巴达摩院推出的开源具身基础模型，基于物理现实构建。提供2B、4B、8B三种稠密模型以及30B-A3B的MoE模型，同时还发布了三个微调后专用模型：用于机器人任务规划的RynnBrain-Plan、视觉语言导航的RynnBrain-Nav、链式点推理的RynnBrain-CoP。

## 主要特性
1.  **全面的第一人称视角理解**：擅长细粒度视频理解和以自我为中心的认知，可完成具身QA、计数、OCR等任务
2.  **多样的时空定位能力**：具备强大的情景记忆定位能力，可精准识别物体、目标区域和运动轨迹
3.  **物理空间推理**：采用文本与空间 grounding 交替的 interleaved 推理策略，让推理过程贴合真实物理环境
4.  **具备物理意识的精准规划**：支持细粒度的操作规划，可在文本推理和定位之间交替进行
