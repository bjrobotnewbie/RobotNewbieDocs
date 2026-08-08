# llama.cpp

**llama.cpp** 是由 Georgi Gerganov 开发的 C/C++ 大语言模型（LLM）推理引擎，是目前 GitHub 上星标数最多的本地 AI 推理框架之一（超过 75,000 颗星）。

## 核心特性

| 特性            | 说明                                                                                                         |
| ------------- | ---------------------------------------------------------------------------------------------------------- |
| **GGUF 格式**   | 专为 llama.cpp 设计的模型格式，支持高效内存映射（mmap）和极速加载                                                                   |
| **广泛量化支持**    | Q2\_K、Q3\_K、Q4\_K\_M、Q5\_K、Q8\_0、FP16 等多种量化方案，大幅降低显存/内存占用                                                  |
| **多硬件后端**     | CPU（AVX-512/AVX2/ARM Neon）、CUDA（NVIDIA）、Metal（Apple Silicon）、Vulkan、SYCL（Intel）、ROCm（AMD）、OpenCL（Qualcomm） |
| **Server 模式** | 内置高性能 HTTP 服务器 `llama-server`，提供 OpenAI 兼容 API                                                             |
| **投机解码**      | 使用小模型预测 token，主模型验证，速度提升 2-3 倍                                                                             |
| **连续批处理**     | 支持多请求并发处理，结合 Prompt Cache 显著提升吞吐量                                                                          |

## 硬件后端支持（2026）

| 后端             | 硬件                         | 状态          |
| -------------- | -------------------------- | ----------- |
| CUDA           | NVIDIA GPU                 | 成熟，性能最优     |
| Metal          | Apple Silicon              | 成熟，表现强劲     |
| ROCm + HIP     | AMD Instinct / RDNA3+      | 成熟          |
| Vulkan         | NVIDIA / AMD / Intel / 移动端 | 成熟，跨平台      |
| SYCL           | Intel Arc / 核显             | 趋于成熟        |
| OpenCL         | Qualcomm Adreno / 移动端      | 趋于成熟        |
| CPU (AVX-512)  | x86 CPU                    | 成熟，CPU 推理最快 |
| CPU (ARM Neon) | ARM CPU / 服务器 / 移动端        | 成熟          |
| CANN           | 华为昇腾                       | 趋于成熟（社区+华为） |

## 快速开始

### 方式一：预编译二进制（最简单）

前往 GitHub Releases 页面下载对应平台的压缩包，解压即可使用：

```bash
# 启动 API Server
./llama-server -m ./your-model.gguf -c 4096 --port 8080

# 交互式对话
./llama-cli -m ./your-model.gguf -p "Hello, introduce yourself" -n 256
```

### 方式二：从源码编译

```bash
git clone https://github.com/ggerganov/llama.cpp
cd llama.cpp

# NVIDIA GPU
cmake -B build -DGGML_CUDA=ON
# Apple Silicon
# cmake -B build -DGGML_METAL=ON
# 纯 CPU
# cmake -B build

cmake --build build --config Release -j $(nproc)
```

### 方式三：Python 绑定

```bash
pip install llama-cpp-python
```

```python
from llama_cpp import Llama

llm = Llama(
    model_path="./qwen2.5-7b-instruct-q4_k_m.gguf",
    n_ctx=4096,
    n_gpu_layers=-1  # -1 表示全部层卸载到 GPU
)
output = llm("Hello, introduce llama.cpp", max_tokens=256)
print(output['choices'][0]['text'])
```

## 支持的模型架构

llama.cpp 支持几乎所有主流开源 LLM 架构，新模型发布后社区通常在几天内完成适配：

- **Llama** 3.x 系列
- **Mistral** / **Mixtral MoE**
- **Qwen** 2.5 / 3 / 3.5 / 3.6
- **Gemma** 2 / 3 / 4
- **Phi-4**
- **DeepSeek** V2 / V3 / V4
- **Command-R**

## 安全提醒

⚠️ **CVE-2026-34159**：llama.cpp < b8492 版本存在 RPC 后端远程代码执行漏洞。请尽快升级至 **b8492 或更高版本**。

## 官方资源

| 资源                 | 链接                                                                                                                                                 |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| 🔗 **GitHub 仓库**   | [github.com/ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp)                                                                             |
| 📦 **预编译下载**       | [GitHub Releases](https://github.com/ggml-org/llama.cpp/releases)                                                                                  |
| 📚 **官方构建文档**      | [github.com/ggml-org/llama.cpp/blob/master/docs/build.md](https://github.com/ggml-org/llama.cpp/blob/master/docs/build.md)                         |
| 📖 **Server 模式文档** | [github.com/ggml-org/llama.cpp/blob/master/examples/server/README.md](https://github.com/ggml-org/llama.cpp/blob/master/examples/server/README) |
| 🤗 **GGUF 模型库**    | [huggingface.co/models?library=gguf](https://huggingface.co/models?library=gguf)                                                                   |

## 生态下游项目

llama.cpp 是许多本地 AI 应用的底层引擎，包括：

- **Ollama** — 友好的模型管理工具
- **LM Studio** — 图形化本地 LLM 客户端
- **GPT4All** — 跨平台本地 AI 助手
- **KoboldCpp** — 面向角色扮演的推理前端
- **llamafile** — 单二进制跨平台可执行文件（Mozilla 项目）

## 适用场景

| 场景         | 推荐理由                                       |
| ---------- | ------------------------------------------ |
| 边缘设备 / 嵌入式 | 零 Python 依赖，单二进制，资源占用极低                    |
| 本地隐私推理     | 数据不出本地，无需 API 费用                           |
| CPU 推理     | 优化的 CPU 后端，普通笔记本即可运行 7B 模型                 |
| 跨平台部署      | 支持 Windows / macOS / Linux / iOS / Android |
| 机器人边缘部署    | 轻量级、低延迟，适合资源受限的机器人平台                       |

