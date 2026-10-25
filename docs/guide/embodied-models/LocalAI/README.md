# LocalAI

LocalAI 是开源 AI 引擎。可在任意硬件上运行各类模型——LLM、视觉、语音、图像、视频模型，无需 GPU。

## 项目链接

- GitHub: <https://github.com/mudler/LocalAI>
- 项目主页: <https://localai.io>
- 中文文档: https://zdoc.app/zh/mudler/LocalAI

## 项目介绍
LocalAI是一款开源AI引擎，支持在任意硬件上运行LLM、视觉、语音、图像、视频等各类AI模型，无需专用GPU。它采用轻量化核心设计，不会强制预装冗余组件，仅在需要对应模型时才拉取对应的后端容器镜像，后端基于llama.cpp、vLLM、whisper.cpp、stable-diffusion、MLX等一流引擎封装。

## 主要特性
1.  **模块化设计**：后端独立按需拉取，仅安装模型所需组件
2.  **开放可扩展**：支持加载任意模型，可通过任意语言基于开放接口自定义后端
3.  **API兼容**：兼容OpenAI、Anthropic、ElevenLabs等主流AI服务API
4.  **多模态支持**：通过统一API提供LLM、视觉、语音、图像、视频全类型模型服务
5.  **硬件无关**：支持NVIDIA、AMD、Intel、Apple Silicon、Vulkan以及纯CPU环境
6.  **企业级能力**：内置API密钥认证、用户配额、角色权限访问控制
7.  **内置AI代理**：支持具备工具调用、RAG、MCP和自定义技能的自主智能体
