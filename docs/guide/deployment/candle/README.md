# Candle

## 简介
Candle 是由 Hugging Face 开源的 Rust 机器学习框架，依托 Rust 语言的特性打造高性能、轻量化的机器学习运行环境。框架语法风格参考 PyTorch，上手门槛低，同时彻底脱离 Python 运行时依赖，可编译为独立二进制程序，能够在服务端、边缘设备、浏览器等多种环境中完成模型推理与训练工作。

## 设计理念
1. 接口风格对标主流深度学习框架，熟悉深度学习开发的开发者可以快速适配使用。
2. 摒弃 Python 解释器与全局解释器锁带来的性能损耗，充分释放硬件算力。
3. 编译产物体积小巧，启动速度快，适配 Serverless、嵌入式设备等对启动效率要求较高的场景。
4. 原生集成硬件加速与模型量化能力，在运行速度和硬件资源占用之间实现良好平衡。

## 功能特性
### 1. 多硬件后端适配
框架支持多款主流硬件与运行环境，可根据部署场景自由切换：
- **CPU**：针对不同系统做专项优化，x86 平台支持 MKL，macOS 平台接入 Accelerate 加速库。
- **CUDA**：完整支持英伟达显卡加速，搭配 cuDNN 算子库提升运算效率，多显卡场景可借助 NCCL 实现分布式运行。
- **Metal**：适配苹果自研芯片，优化矩阵运算等核心计算逻辑。
- **WASM**：模型可直接在浏览器中运行，无需额外后端服务支撑，实现纯前端 AI 能力。

### 2. 算子与模型格式支持
- 内置完整的张量运算、网络层组件、数据加载工具，满足常规模型开发需求。
- 支持 Flash Attention v2 等主流优化算子，也可自定义算子并嵌入框架使用。
- 兼容 safetensors、npz、ggml、PyTorch 等多种主流模型文件格式，模型迁移便捷。
- 集成类 llama.cpp 量化方案，通过量化压缩模型体积，降低运行资源开销。

### 3. 丰富的预训练模型生态
对接 Hugging Face 模型社区，覆盖当下主流人工智能任务，开箱即可使用：
- 大语言模型：LLaMA 系列、Mistral、Mixtral、Gemma、Phi、Qwen、RWKV 等
- 文本任务模型：T5、Marian-MT、CoEdit 等，支持翻译、文本纠错等场景
- 图像生成模型：Stable Diffusion、Wurstchen
- 语音模型：Whisper、EnCodec、Parler-TTS，覆盖语音识别、语音合成领域
- 计算机视觉模型：YOLO、SAM、DINOv2、ViT、SegFormer、ResNet 等
- 多模态模型：BLIP、TrOCR、CLIP

### 4. 工程化能力
- 完整支持模型训练、推理全链路开发。
- 项目内置大量示例代码与浏览器在线演示案例，便于参考调试。
- 兼容 ONNX 模型格式，方便不同框架之间的模型迁移部署。
- 完善的异常捕获与编译优化策略，适配正式生产环境使用。

## 项目模块划分
项目采用模块化拆分，各模块职责清晰，可按需引入使用：
- `candle-core`：实现张量定义、设备管理、基础运算逻辑
- `candle-nn`：提供神经网络基础层与组件，用于搭建网络结构
- `candle-examples`：各类功能、场景的示例代码
- `candle-kernels`：CUDA 平台专属定制算子
- `candle-datasets`：数据集处理与数据加载工具
- `candle-transformers`：Transformer 架构模型配套工具
- `candle-flash-attn`：Flash Attention v2 算子实现
- `candle-onnx`：ONNX 格式模型推理支持
- `candle-pyo3`：提供 Python 绑定，实现 Rust 与 Python 互调用
- `candle-wasm-examples`：浏览器 WASM 环境运行示例

## 快速上手
### 环境准备
确保本地已安装 Rust 编译环境，执行以下命令新建项目并引入依赖：
```bash
cargo new candle-demo
cd candle-demo
```
修改 `Cargo.toml`，添加框架依赖：
```toml
[dependencies]
candle-core = "latest-version"
```

### 基础示例：张量矩阵乘法
编辑 `src/main.rs`，编写基础张量运算代码：
```rust
use candle_core::{Device, Tensor};

fn main() -> Result<(), Box<dyn std::error::Error>> {
    // 指定运行设备为 CPU
    let device = Device::Cpu;
    // 生成两组随机张量
    let a = Tensor::randn(0f32, 1., (2, 3), &device)?;
    let b = Tensor::randn(0f32, 1., (3, 4), &device)?;
    // 执行矩阵乘法
    let c = a.matmul(&b)?;
    // 打印结果
    println!("计算结果：\n{}", c);
    Ok(())
}
```

### 运行代码
1. CPU 环境运行
```bash
cargo run
```
执行后会输出形状为 `[2, 4]` 的张量数据。

2. CUDA 显卡环境运行
修改设备配置，并在编译时开启 CUDA 特性：
```rust
let device = Device::new_cuda(0)?;
```
运行命令：
```bash
cargo run --features cuda
```

## 常用操作对照（Candle 与 PyTorch）
熟悉 PyTorch 的开发者可参考下表快速切换语法：

| 操作功能 | PyTorch | Candle |
| ---- | ---- | ---- |
| 手动创建张量 | `torch.Tensor([[1,2],[3,4]])` | `Tensor::new(&[[1f32,2.],[3.,4.]], &Device::Cpu)?` |
| 创建全零张量 | `torch.zeros((2,2))` | `Tensor::zeros((2,2), DType::F32, &Device::Cpu)?` |
| 张量切片 | `tensor[:, :4]` | `tensor.i((.., ..4))?` |
| 形状重塑 | `tensor.view((2,2))` | `tensor.reshape((2,2))?` |
| 矩阵乘法 | `a.matmul(b)` | `a.matmul(&b)?` |
| 设备迁移 | `tensor.to("cuda")` | `tensor.to_device(&Device::new_cuda(0)?)?` |
| 模型保存 | `torch.save(...)` | `safetensors::save(...)` |

## 适用场景
1. **边缘/Serverless 推理**：程序体积小、冷启动速度快，适配资源受限的部署环境。
2. **无 Python 运维环境**：纯 Rust 二进制部署，无需配置 Python 环境，简化运维流程。
3. **前端浏览器 AI**：依托 WASM 能力，在网页端直接运行各类模型，无需后端接口转发。
4. **高性能服务部署**：结合 GPU 加速与模型量化，提升推理效率、降低硬件消耗。
5. **模型工具开发**：可用于模型量化、格式转换、推理服务封装等工具类开发。

## 框架优势
1. 接口设计友好，沿用主流深度学习框架使用习惯，学习成本低。
2. 基于 Rust 开发，具备内存安全、无垃圾回收的特性，运行稳定且高效。
3. 全平台多后端兼容，跨系统部署一致性表现良好。
4. 深度对接 Hugging Face 模型生态，海量预训练模型可直接调用。
5. 内置多种优化方案，推理性能表现优异。
6. 完全脱离 Python 依赖，满足轻量化、嵌入式、私有化部署需求。

## 相关链接
- 代码仓库：https://github.com/huggingface/candle
- 官方文档：https://huggingface.github.io/candle/