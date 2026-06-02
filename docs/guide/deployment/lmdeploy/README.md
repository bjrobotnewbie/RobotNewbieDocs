# LMDeploy

LMDeploy 是由 MMRazor 与 MMDeploy 团队研发，面向大语言模型与多模态模型的轻量化、高性能部署工具链，集模型量化、推理优化、服务部署于一体，助力开发者快速将模型落地到生产环境。

## 关键能力

### 1. 高效推理

- 采用 Persistent Batch（连续批处理）、Blocked KV Cache、动态拆分融合、张量并行、高性能 CUDA Kernel 等优化手段
- 请求吞吐量相较 vLLM 最高提升约 1.8 倍
- 支持多轮对话缓存 KV，复用历史上下文，降低重复计算开销

### 2. 可靠量化

- 支持权重量化与 KV 量化
- 4bit 推理性能较 FP16 提升约 2.4 倍
- 量化效果经 OpenCompass 评测验证，兼顾精度与速度

### 3. 便捷服务分发

- 内置请求分发能力，支持多模型在多机、多 GPU 环境下统一调度
- 开箱即用的 OpenAI 兼容接口，降低接入成本
- 支持 LLM 与 VLM 统一服务化部署，简化多模态架构

### 4. 广泛兼容

- 兼容 KV Cache 量化、AWQ、Automatic Prefix Caching 等特性组合使用
- 支持 NVIDIA、华为昇腾、寒武纪、沐曦等多种硬件平台
- 提供 TurboMind 与 PyTorch 双推理引擎，适配性能与开发灵活度需求

## 双引擎架构

LMDeploy 提供两套推理引擎，满足不同场景：
\| 引擎 | 定位 | 特点 |
\| : | : | : |
\| **TurboMind** | 极致推理性能 | C++/CUDA 深度优化，低延迟、高吞吐 |
\| **PyTorch** | 易用与二次开发 | 纯 Python 实现，便于调试、扩展与新模型适配 |

## 支持模型范围

### 大语言模型（LLM）

- Llama 系列 / Llama2 / Llama3 / Llama3.1 / Llama3.2
- InternLM / InternLM2 / InternLM2.5 / InternLM3
- Qwen / Qwen1.5 / Qwen2 / Qwen2.5 / Qwen3 系列
- Baichuan / Baichuan2、ChatGLM2 / GLM4、Mistral / Mixtral、DeepSeek 系列、Gemma、Phi 系列等

### 视觉语言模型（VLM）

- LLaVA、InternLM-XComposer、Qwen-VL / Qwen2-VL、DeepSeek-VL、InternVL、CogVLM、MiniCPM-V 等多模态模型

## 快速上手

### 1. 安装（推荐 Conda 环境）

```bash
conda create -n lmdeploy python=3.10 -y
conda activate lmdeploy
pip install lmdeploy
```

### 2. 离线批量推理

```python
import lmdeploy

with lmdeploy.pipeline("internlm/internlm3-8b-instruct") as pipe:
    responses = pipe(["Hi, pls intro yourself", "Shanghai is"])
    print(responses)
```

### 3. 启动兼容 OpenAI 服务

```bash
lmdeploy serve api_server internlm/internlm3-8b-instruct
```

启动后可通过 `http://0.0.0.0:23333/v1/chat/completions` 调用，兼容 OpenAI SDK。

## 典型使用场景

- 单卡/多卡大模型离线批量推理
- 生产环境高并发 LLM 接口服务
- 多模型、多机负载均衡分发
- 4bit/8bit 量化模型低资源部署
- 多模态（图文）模型端到端服务化

## 文档与社区

- 官方文档：<https://lmdeploy.readthedocs.io/zh-cn/latest/>
- 中文文档：<https://lmdeploy.readthedocs.io/zh-cn/latest/>
- 代码仓库：<https://github.com/InternLM/lmdeploy>
- 协议：Apache 2.0

