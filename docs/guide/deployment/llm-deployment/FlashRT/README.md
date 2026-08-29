# FlashRT

FlashRT 是一款专为小批量、低延迟 AI 工作负载设计的高性能实时推理引擎。旗舰集成包括 Pi0、Pi0.5、GROOT N1.6 和 Pi0-FAST 的量产 VLA 控制。此外还支持 LLM 模型，例如 Qwen3.6-27B。

## 项目链接

- GitHub: <https://github.com/flashrt-project/FlashRT>

## 项目介绍
FlashRT是一款面向小批量、低延迟AI推理工作负载的高性能实时推理引擎。它无需ONNX导出、无需引擎编译、无需逐驱动重新构建，通过手写定制内核覆盖标准Transformer、DiT、SigLIP等模型原语，且硬件适配架构无关，当前已支持从边缘端Jetson AGX Thor到服务器端A100、RTX 4090/5090的NVIDIA设备。

其核心落地场景为VLA控制，已在Pi0、Pi0.5、GROOT N1.6/1.7、Pi0-FAST等产品中完成验证，同时支持BAGEL世界模型研究、Higgs Audio v3 TTS、Wan2.2/Motus视频策略推理，以及Qwen3.6-27B的NVFP4单流LLM长上下文推理。

## 主要特性
1.  零编译开销：无需提前导出模型或编译引擎，直接部署
2.  定制化手写内核：覆盖归一化、激活融合、RoPE、FP8、NVFP4 GEMM、注意力等关键算子
3.  硬件适配广泛：支持NVIDIA从边缘到全系列服务器显卡
4.  针对性优化：针对小批量实时推理场景设计，对比传统推理工具在低延迟任务上性能优势显著，例如在Jetson AGX Thor上可将Pi0.5策略推理延迟从303.6ms优化至29.2ms，帧率提升至34.2Hz。
