# Crane

基于纯 Rust 的 LLM、VLM、VLA、TTS 和 OCR 推理引擎，由 Candle 和 Rust 驱动。作为 llama.cpp 的替代品，更加简单和整洁。

## 项目链接

- GitHub: <https://github.com/lucasjinreal/Crane>

## 项目介绍
Crane是一款基于Rust和Candle框架开发的高性能AI推理引擎，可作为llama.cpp的轻量替代方案。它支持LLM、VLM、VLA、TTS、OCR等多种AI模型的本地推理，可在CPU、CUDA、Metal设备上快速运行，相比原生PyTorch在苹果芯片上最高可提速50倍。项目代码简洁易维护，可直接编译为二进制文件，同时兼容OpenAI和SGLang接口。

## 主要特性
1.  **极速推理**：基于Candle优化内核，性能优于原生PyTorch
2.  **Rust原生开发**：无需复杂C++代码，兼顾性能与开发效率
3.  **多硬件支持**：统一代码库兼容CPU、CUDA、Metal加速
4.  **开箱即用**：内置LLM聊天、VLM聊天、OCR、TTS、ASR、VAD等多种AI能力
5.  **丰富模型支持**：已支持Qwen系列、Gemma4、PaddleOCR、Moonshine ASR、多款TTS模型等，后续还将新增Qwen3.5-VLA等模型
