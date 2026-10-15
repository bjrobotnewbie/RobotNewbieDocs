# flux-action

FLUX 3 动作模型：从 Black Forest Labs 下载 7B 世界动作模型。支持对机器人（DROID、SO-101）、仿真器和游戏进行训练、微调及动作预测。

## 项目链接

- GitHub: <https://github.com/black-forest-labs/flux-action>
- 项目主页: <https://bfl.ai/models/flux-3-action>

## 项目介绍
flux-action是Black Forest Labs推出的开源权重7B世界动作模型，核心功能是基于相机帧、机器人状态和文本指令，输出机器人（DROID、SO-101）、模拟器或游戏的下一段动作，同时与下一视频帧协同去噪。本仓库提供该模型的独立训练与推理代码，支持自定义任务与实体适配，还集成了LeRobot工具链，可实现模型的微调与部署。

## 主要特性
1. 开源权重7B动作模型，支持机器人、模拟器、游戏的动作预测；
2. 提供独立的训练与推理实现，区分训练、BF16推理、FP8r推理分支，便于理解与使用；
3. 针对DROID、SO-101提供多精度（BF16/FP8r）、多配方（基础、蒸馏、单步）的权重包，适配不同场景需求；
4. 支持全量微调、LoRA微调，可自定义任务与实体，附带详细使用指南。
