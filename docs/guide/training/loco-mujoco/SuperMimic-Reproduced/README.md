# SuperMimic-Reproduced

SuperMimic 复现（arXiv:2610.28480）：学习可微世界模型 + BPTT 策略用于 G1 人形机器人运动追踪，部署于 mjlab/MuJoCo Warp

## 项目链接

- GitHub: <https://github.com/CuboiLeo/SuperMimic-Reproduced>

## 项目介绍
本项目是SuperMimic（arXiv:2610.28480）的独立从零复现，基于mjlab/MuJoCo Warp构建，核心为可微世界模型结合短视野BPTT actor-critic，用于Unitree G1人形机器人全身动作跟踪。项目复现了原论文的核心组件，包括LAFAN1、BONES-SEED动作库数据管线、可微FK、奖励头、世界模型与训练器，支持torchrun数据并行训练，还包含附录F基准测试与交互式回放查看器。

## 主要特性
1. 核心算法复现：实现可微世界模型、BPTT策略训练，支持全身动作跟踪任务；
2. 数据与训练支持：集成LAFAN1、BONES-SEED动作库，支持单卡/多卡数据并行训练，适配RTX 5090等硬件；
3. 性能表现：在LAFAN1数据集上，锚点相对观测配置下1.66小时即可达到原论文0.82的跟踪分数，部分场景达0.904；BONES-SEED数据集上训练4.2小时回报达0.934；
4. 完整文档：包含论文规范转录、复现计划、审查日志、实验日志等，便于复现与验证。
