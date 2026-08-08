# xtuner

XTuner 是 InternLM 生态中的大模型训练引擎，重点面向超大规模 MoE 模型的高效训练。

## 项目链接

- GitHub: <https://github.com/InternLM/xtuner>
- 项目主页: https://xtuner.readthedocs.io/zh-cn/latest/

## 项目概述

XTuner V1 面向超大规模混合专家模型训练，目标是在主流学术和工业训练场景中降低并行复杂度并提升吞吐。项目强调 dropless training、长序列训练、MoE 大模型训练效率、DeepSpeed Ulysses 序列并行，以及在 NVIDIA GPU 和昇腾 NPU 等硬件上的优化。

它不仅服务于预训练和指令微调，也规划支持强化学习相关训练流程。对于需要训练数百亿到万亿参数级 MoE 模型的团队，XTuner 提供了围绕 FSDP、序列并行、专家并行和硬件适配的系统化训练能力；对于研究者，它也提供了模型、配置和文档入口，方便复用 InternLM 相关训练实践。
