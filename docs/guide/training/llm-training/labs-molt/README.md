# labs-molt

面向研究用途的代理优先强化学习框架（9000 行代码）。

## 项目链接

- GitHub: <https://github.com/NVIDIA-NeMo/labs-molt>

## 项目介绍
Molt是一款面向研究场景的agent优先型RL框架，代码量约9.2K行，基于PyTorch原生开发，采用轻量技术栈：Ray负责调度与异步队列、vLLM用于采样生成、NVIDIA AutoModel+FSDP2实现训练。它支持万亿参数级别的全异步多模态多轮智能体强化学习，可适配DeepSeek-V3等大模型训练。

## 主要特性
1.  **agent优先设计**：将智能体作为核心程序，训练器仅为单actor，奖励函数可通过自定义Env或ChatAgent实现，支持 grader、多轮工具、VLM环境、LLM-as-judge等多种奖励形式
2.  **轻量化技术栈**：仅依赖PyTorch、Ray、vLLM、NVIDIA AutoModel，支持张量并行(TP)、专家并行(EP)、上下文并行(CP)，可开启Adam CPU offload适配超大型智能体
3.  **统一接口规范**：采用token-first数据契约，从采样到训练全程保持token id、logprobs、动作范围、奖励、多模态张量对齐，一套API即可完成全流程开发
4.  适配科研场景：代码简洁可通读，提供快速上手教程、示例方案与性能调优指南，配套技术报告可供参考。
