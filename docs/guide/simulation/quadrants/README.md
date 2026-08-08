# quadrants

Quadrants 是面向物理仿真和机器人负载的高性能多平台编译器，可将 Python 代码编译为并行 kernel。

## 项目链接

- GitHub: <https://github.com/Genesis-Embodied-AI/quadrants>
- 项目主页: https://genesis-embodied-ai.github.io/quadrants/user_guide/index.html

## 项目概述

Quadrants 由 Genesis AI 持续开发，面向大规模物理仿真和机器人工作负载。它可以把 Python 代码编译成高度优化的并行内核，运行在 NVIDIA CUDA、Vulkan/SPIR-V、Apple Metal、AMD ROCm HIP 以及 x86/ARM64 CPU 上，为跨平台高性能仿真提供底层执行能力。

该项目源自 Taichi 分支，但已经独立演进，不追求与上游完全兼容。Quadrants 强调多平台支持、kernel 级覆盖率、dataclass 结构、结构化编译和面向物理仿真的工程改进。它适合作为 Genesis World 等仿真系统的编译后端，也适合研究者构建需要 GPU/CPU 高并行的自定义物理计算。
