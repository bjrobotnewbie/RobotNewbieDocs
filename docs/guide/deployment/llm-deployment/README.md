# 大模型部署

大语言模型（LLM）推理与部署框架，涵盖高性能云端推理服务和本地/边缘部署方案。这些框架支持将大模型部署到机器人平台，用于 VLA（视觉语言动作）模型推理、对话交互等场景。

## 高性能推理服务

适用于数据中心和云端的大模型推理服务框架，提供高吞吐、低延迟的推理能力。

| 项目 | 核心特性 | 性能优势 | 适用场景 |
| ---- | -------- | -------- | -------- |
| [vLLM](/guide/deployment/llm-deployment/vllm/README) | PagedAttention, 连续批处理 | 吞吐量提升 2-4x | 高吞吐量云端推理 |
| [TensorRT-LLM](/guide/deployment/llm-deployment/tensorrt-llm/README) | NVIDIA 官方, AutoDeploy, FP8 | 极致延迟优化 | 数据中心生产环境 |
| [LMDeploy](/guide/deployment/llm-deployment/lmdeploy/README) | TurboMind 引擎, AWQ 4bit | 中文模型优化 | 国内生态友好 |
| [Text Generation Inference](/guide/deployment/llm-deployment/text-generation-inference/README) | Hugging Face 官方, 流式输出 | 生产级稳定性 | 企业级服务部署 |

## 本地与边缘部署

专为资源受限的边缘设备设计的轻量级推理框架和优化技术。

| 项目 | 核心特性 | 典型设备 | 适用场景 |
| ---- | -------- | -------- | -------- |
| [Ollama](/guide/deployment/llm-deployment/ollama/README) | 单二进制, 一键启动 | x86/ARM 桌面 | 快速原型验证 |
| [llama.cpp](/guide/deployment/llm-deployment/llama_cpp/README) | C/C++ 实现, GGUF 格式, 零 Python 依赖 | 嵌入式设备 / Jetson / Raspberry Pi | 资源受限环境, 本地隐私推理 |
| [Candle](/guide/deployment/llm-deployment/candle/README) | Rust 实现, 零 Python 依赖 | 嵌入式设备 | 资源受限环境 |

> **llama.cpp** 是目前 GitHub 上星标数最多的本地 AI 推理框架（超过 75,000 颗星），支持从 CPU 到 CUDA/Metal/Vulkan 等几乎所有主流后端，是机器人边缘部署的首选方案之一。

- [OM1（面向机器人的模块化AI HAL（硬件抽象…）](/guide/deployment/llm-deployment/OM1/README)

- [cactus（面向移动设备、可穿戴设备、智能家居及机器…）](/guide/deployment/llm-deployment/cactus/README)

- [needle（适用于微型设备的基座模型；14MB 参数…）](/guide/deployment/llm-deployment/needle/README)
