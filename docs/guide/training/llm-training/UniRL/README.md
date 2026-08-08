# UniRL

UniRL 是腾讯混元开源的统一多模态强化学习框架，面向扩散、AR、理解和统一模型的后训练。

## 项目链接

- GitHub: <https://github.com/Tencent-Hunyuan/UniRL>
- 项目主页: https://unirl-project.github.io/unirl/

## 项目概述

UniRL 将强化学习后训练抽象为一条统一流程：生成样本、打分、计算优势、更新策略，并同步权重到 rollout worker。它通过分层系统支持不同模型家族，包括扩散模型、自回归模型、感知/理解模型和统一多模态模型，每类模型都有对应 trainer，并通过 Hydra 配置描述模型、算法、rollout、奖励、资源放置和同步方式。

项目内置 DRPO、Flow-DPPO、CPPO 等团队提出的算法，也连接 GRPO、DiffusionNFT、DanceGRPO、MixGRPO 等参考算法。它适合研究多模态模型的 RL 后训练，尤其是文本到图像、图像理解、统一生成理解模型以及 diffusion/flow matching 策略优化场景。
