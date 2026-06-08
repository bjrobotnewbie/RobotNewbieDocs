# OpenVLA
开源的通用视觉-语言-动作（VLA）模型，基于Prismatic VLM架构（融合DINOv2和SigLIP视觉主干，搭配Llama-2 LLM），支持开箱即用，可直接生成机器人可执行的控制命令。

## 核心特性
- 基于100万+机器人交互轨迹预训练，具备极强的泛化能力
- 支持零样本和少样本迁移到新机器人、新任务、新场景
- 原生支持LIBERO、ALOHA、RLBench等主流机器人基准平台
- 提供7B参数版本，兼顾性能与部署成本
- 支持多种机器人构型：单臂、双臂、移动操作机器人等

## 相关链接
- 📦 GitHub仓库：[https://github.com/openvla/openvla](https://github.com/openvla/openvla)
- 🤗 HuggingFace权重：[https://huggingface.co/openvla/openvla-7b](https://huggingface.co/openvla/openvla-7b)
- 🐼 ModelScope权重：[https://modelscope.cn/models/OpenRobotLab/OpenVLA-7B](https://modelscope.cn/models/OpenRobotLab/OpenVLA-7B)
- 📚 官方文档：[https://openvla.github.io](https://openvla.github.io)
