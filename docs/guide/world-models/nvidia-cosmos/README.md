# NVIDIA Cosmos

- 官方文档：[NVIDIA Cosmos](https://docs.nvidia.com/cosmos/)

**NVIDIA Cosmos™** 是英伟达专为**物理AI**打造的开发平台，核心组件包括：

| 组件 | 说明 |
|:---|:---|
| **世界基础模型 (WFMs)** | 最先进的生成式模型，用于模拟物理世界 |
| **护栏机制 (Guardrails)** | 安全约束与合规控制 |
| **加速数据处理管线** | 高效的数据筛选与整理流程 |

**应用场景**：开发者利用 Cosmos 加速三类物理 AI 的开发——
- 自动驾驶汽车 (AVs)
- 机器人
- 视频分析 AI 智能体

## Cosmos 3

**Cosmos 3: Omnimodal World Models for Physical AI**

Cosmos 3 是 NVIDIA 推出的全模态世界模型，通过共享的全模态世界模型连接理解、生成、仿真和动作，能够流畅地在文本、图像、视频、音频和动作之间转换。

### 核心特点

- **统一架构**：采用 Cosmos 3 Unified MoT 架构，自回归扩散模型
- **全模态支持**：支持语言、图像、视频、音频、动作多种模态
- **多任务能力**：
  - **视觉语言推理**：在物理世界中进行推理，理解空间关系、时间线索、物体状态和动作
  - **图像生成**：根据语言描述生成具有物理细节的真实场景图像
  - **视听生成**：从文本、图像或片段生成具有物理感知的视频，并可为运动匹配合适的音频
  - **机器人策略**：将感知转化为动作，遵循指令将视觉上下文转化为有目的的规划和操作
  - **前向动力学**：根据观测和控制预测未来视频，帮助智能体预览结果，用于规划、评估和数据生成
  - **逆动力学**：从观测状态中恢复解释场景变化的轨迹或控制，将视频证据转化为动作

### 性能表现

Cosmos 3 在多项基准测试中排名第一：
- 在机器人、智能空间和驾驶基准平均排名第一，展现出强大的物理世界理解能力
- 在文本到图像、图像到视频和机器人策略方面排名第一

### 相关链接

- 中文介绍：[使用 NVIDIA Cosmos 3 开发物理 AI 推理世界和动作模型](https://developer.nvidia.cn/blog/develop-physical-ai-reasoning-world-and-action-models-with-nvidia-cosmos-3/)
- 英文官网：[Cosmos 3 — Cosmos Lab](https://research.nvidia.com/labs/cosmos-lab/cosmos3/)
- GitHub 代码：[https://github.com/NVIDIA/cosmos-framework](https://github.com/NVIDIA/cosmos-framework)
- 技术报告：[https://research.nvidia.com/labs/cosmos-lab/cosmos3/technical-report.pdf](https://research.nvidia.com/labs/cosmos-lab/cosmos3/technical-report.pdf)
- Hugging Face 模型：[https://huggingface.co/collections/nvidia/cosmos3](https://huggingface.co/collections/nvidia/cosmos3)