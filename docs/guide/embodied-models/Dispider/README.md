# Dispider

[CVPR 2025] Dispider：通过解耦感知、决策与反应实现支持主动实时交互的视觉语言模型

## 项目链接

- GitHub: <https://github.com/Mark12Ding/Dispider>

## 项目概述

## 项目介绍
Dispider是CVPR 2025收录的论文官方实现，旨在通过解耦感知、决策和反应模块，让视频大语言模型（Video LLMs）具备实时主动交互能力。
该系统可持续感知输入视频，判断是否需要响应用户指令，仅在触发条件满足时调用更大的反应模型。项目提供离线推理、带时间戳答案的增量推理、可选的决策KV缓存以及OVO-Bench评估工具。

## 主要特性
1.  **模块化架构**：
    - 感知模块：使用CLIP视觉塔编码16帧采样片段
    - 感知-决策模块：基于Qwen2-1.5B构建时序记忆
    - 决策模块：基于紧凑型模型的决策头，判断是否触发响应
    - 反应模块：基于Qwen2-7B在触发后生成回答
2.  支持多种推理模式：离线推理、带时间戳的增量推理、可选决策KV缓存
3.  提供轻量化的部署代码，仅保留Dispider专属的感知、记忆、决策、流式推理和反应推理逻辑
4.  配套了标准的模型API接口，包含Perception、PerceptionDecision、Decision和Reaction四类组件
5.  提供了详细的安装部署流程，验证环境为Python 3.10、CUDA 12.1、PyTorch 2.2.0+cu121等版本，同时提供了HuggingFace模型 checkpoint下载方式。
