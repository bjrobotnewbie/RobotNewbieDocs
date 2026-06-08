# LingBot-VA

Causal video-action world model for generalist robot control

**RSS 2026**

LingBot-VA 是一个统一视频世界建模和策略学习的自回归框架，联合学习未来帧预测和动作执行，是面向通用机器人控制的因果视频-动作世界模型。

## 核心思想

LingBot-VA 是一个自回归扩散框架，在单个交错序列中将视觉动态预测和动作推理架构统一。它使机器人能够同时推理未来状态并执行精确的闭环控制。

## 工作流程

### 大规模预训练

在大规模机器人视频-动作数据集上预训练 LingBot-VA，学习丰富的视觉动态，为理解物理世界如何演化和在其中操作建立坚实基础。

### 三阶段框架

1. **自回归视频生成**：根据当前观测和语言指令预测未来帧
2. **逆动力学模型（IDM）**：从预测视频中解码动作
3. **闭环控制**：执行后，真实观测替换视频 KV 缓存，使视频-动作模型基于实际结果，实现闭环控制

逆动力学模型（IDM）能够从预测视频中准确解码动作，在不同环境和机器人形态上都有良好的泛化能力。

## 核心优势

### 长期记忆

能够记住完整历史并正确行动。在包含重复状态的序列任务中，模型可以区分不同上下文下的相同状态，例如在状态序列 A → B → A → C 中，能正确学习到 P(C|A→B→A)=1。

### 少样本适应

能够快速学习。由于自回归视频模型的长期记忆和样本效率优势，能够快速适应新任务。

## 性能表现

LingBot-VA 是一个多功能全才，在广泛场景中表现出色：
- **长周期任务**：制作早餐、拆包裹
- **高精度控制**：插入管子、拧螺丝
- **可变形和关节物体操作**：叠衣服、开抽屉

在 RoboTwin 2.0 和 LIBERO 两个仿真基准测试中，相比现有最优方法持续改进。

## 相关链接

- 项目网站：[https://technology.robbyant.com/lingbot-va](https://technology.robbyant.com/lingbot-va)
- GitHub 代码：[https://github.com/Robbyant/lingbot-va](https://github.com/Robbyant/lingbot-va)
- ModelScope：[https://www.modelscope.cn/collections/Robbyant/LingBot-va](https://www.modelscope.cn/collections/Robbyant/LingBot-va)
- Hugging Face：[https://huggingface.co/collections/robbyant/lingbot-va](https://huggingface.co/collections/robbyant/lingbot-va)
- 技术报告：[https://github.com/Robbyant/lingbot-va/blob/master/LingBot_VA_paper.pdf](https://github.com/Robbyant/lingbot-va/blob/master/LingBot_VA_paper.pdf)
