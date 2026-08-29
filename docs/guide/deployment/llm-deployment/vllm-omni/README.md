# vllm-omni

支持多模态模型的高效推理框架

## 项目链接

- GitHub: <https://github.com/vllm-project/vllm-omni>
- 项目主页: <https://docs.vllm.ai/projects/vllm-omni>

## 项目介绍
vllm-omni是一款面向多模态模型的高效推理框架，主打简单易用、快速且低成本的多模态模型服务，旨在帮助开发者便捷部署各类多模态模型。项目依托vLLM生态，支持多种硬件平台，提供完整的文档、社区论坛与技术支持渠道。

## 主要特性
1.  **核心能力**：支持文本、图像、视频、音频、TTS、机器人策略等多类型模态的模型推理与服务部署
2.  **性能优化**：支持请求级/逐步骤批处理、FA3加速、分布式分层扩散卸载、异步输出物化等优化手段，大幅提升推理效率
3.  **版本更新**：持续对齐vLLM官方版本，已支持MiniMax H3音视频生成、MiniCPM-o 4.5实时全双工、LTX-2.3、Qwen3-Omni、Qwen-Image-Edit等多款主流多模态模型
4.  **硬件兼容**：覆盖CUDA、ROCm、XPU、NPU等多类硬件平台，同时支持量化、流式推理等部署需求
5.  **拓展生态**：配套VeRL-Omni项目，可实现基于vLLM-Omni的扩散RL训练与部署
