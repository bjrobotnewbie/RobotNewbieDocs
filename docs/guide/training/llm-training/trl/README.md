# trl

TRL 是 Hugging Face 的基础模型后训练库，支持 SFT、GRPO、DPO、奖励建模等语言模型训练方法。

## 项目链接

- GitHub: <https://github.com/huggingface/trl>
- 项目主页: http://hf.co/docs/trl

## 项目概述

TRL（Transformers Reinforcement Learning）是 Hugging Face 生态中用于基础模型后训练的综合库。它建立在 Transformers、Accelerate、PEFT 等工具之上，支持监督微调、偏好优化、强化学习式后训练和奖励模型训练，适用于语言模型以及更广泛的多模态/模型架构后训练场景。

README 中强调 TRL v1 标志着项目定位从“强化学习训练语言模型”扩展为“基础模型后训练库”。它提供多个 Trainer，例如 SFTTrainer、GRPOTrainer、DPOTrainer、RewardTrainer 等，使用户可以用统一接口完成常见后训练方法。项目还支持 Accelerate、DeepSpeed、PEFT、LoRA/QLoRA、Unsloth 优化和命令行训练方式，便于从单卡扩展到多节点集群。

TRL 适合大语言模型微调、偏好对齐、RLHF/RLAIF、GRPO、DPO、奖励模型训练和模型后训练实验。对于已经使用 Hugging Face Transformers 的团队，它提供了与现有模型、数据集、Hub 和训练基础设施紧密集成的后训练工具链。