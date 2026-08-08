# needle

适用于微型设备的基座模型；14MB 参数规模，1-6K tokens/秒的推理速度，支持移动设备、可穿戴设备、智能家居及机器人场景。

## 项目链接

- GitHub: <https://github.com/cactus-compute/needle>
- 项目主页: <https://cactuscompute.com>

## 项目概述

## 项目介绍
Needle是一款面向小型设备的基础大模型，参数规模为2600万，仅14MB体积，可在手机、可穿戴设备、智能家居和机器人上实现1-6k tokens/秒的推理速度，生产环境下在Cactus框架中可达到6000 tokens/秒预填充、1200 tokens/秒解码的性能。
它基于Simple Attention Network架构，支持本地在Mac/PC上微调，权重与数据集生成代码完全开源，可在Hugging Face获取。模型采用12层编码器、8层解码器架构，使用BPE 8192分词器，支持工具调用功能。

## 主要特性
1.  轻量高效：体积仅14MB，适配各类边缘小型设备
2.  支持本地微调：可在普通个人电脑上完成模型微调
3.  擅长工具调用：在单轮工具调用任务上性能优于FunctionGemma-270m、Qwen-0.6B等同类小模型
4.  训练高效：预训练仅使用16颗TPU v6e训练27小时，后续微调仅需45分钟
