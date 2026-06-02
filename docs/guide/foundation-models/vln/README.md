# 视觉语言导航模型

视觉语言导航模型是具身智能的重要分支，目标是让机器人在自然语言指令引导下，在真实或虚拟环境中自主导航到目标地点。这类模型结合了视觉感知、语言理解和路径规划能力，是服务机器人、自主移动机器人等场景的核心技术之一。

## 目录

- [CLIPort](/guide/foundation-models/vln/cliport/README.md)
- [VLN-BERT](/guide/foundation-models/vln/vln-bert/README.md)
- [DUET](/guide/foundation-models/vln/duet/README.md)
- [DualVLN](/guide/foundation-models/vln/dualvln/README.md)
- [SkillNav](/guide/foundation-models/vln/skillnav/README.md)
- [UrbanNav](/guide/foundation-models/vln/urbannav/README.md)
- [JanusVLN](/guide/foundation-models/vln/janusvln/README.md)

## 什么是视觉语言导航(VLN)

VLN任务要求机器人接收自然语言指令（如"去厨房拿一瓶可乐"），并通过视觉感知环境，自主规划并执行从当前位置到目标位置的导航路径。与传统导航不同，VLN需要理解语言指令中的语义信息，并将其与视觉环境进行匹配。

## 核心优势

1. **语义理解**：能够理解自然语言指令中的抽象语义
2. **环境适配**：适应未知或半结构化环境
3. **自主规划**：无需人工干预即可完成导航任务
4. **多模态融合**：整合视觉、语言、空间等多模态信息

## 开源项目

### CLIPort

CLIPort是一个语言条件下的模仿学习智能体，可以学习单一的多任务策略，用于各种桌面操作任务

### VLN-BERT

VLN-BERT是基于BERT的视觉语言导航模型，通过循环神经网络增强，能够在导航过程中更好地理解历史信息和语言指令

### DUET

DUET是基于双尺度图Transformer的视觉语言导航模型，能够同时进行全局动作规划和细粒度跨模态理解

### DualVLN

DualVLN是首个双系统视觉语言导航基础模型，通过协同集成高层推理与低层动作执行，实现了出色的泛化能力和实时控制性能

### SkillNav

SkillNav是基于技能的模块化VLN框架，将导航学习分解为可重用的原子技能，实现灵活重组和泛化能力

### UrbanNav

UrbanNav是从网络规模人类轨迹中学习语言引导的城市导航方法，支持室外大规模环境导航

### JanusVLN

JanusVLN是西安交通大学提出的新型视觉语言导航框架，受人类大脑功能分区启发，解耦语义理解与几何空间推理，采用双隐式记忆机制分别压缩视觉语义特征和3D空间表示。

更多项目正在陆续添加中...
