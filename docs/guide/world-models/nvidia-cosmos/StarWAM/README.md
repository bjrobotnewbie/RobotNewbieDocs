# StarWAM

适用于世界 - 动作模型的通用代码库

## 项目链接

- GitHub: <https://github.com/shaohua-pan/StarWAM>

## 项目介绍
StarWAM是一个通用的世界-动作模型（WAM）研究代码库，用于构建结合生成式视频/世界模型与动作预测模块的机器人策略，支持对世界模型骨干、动作表示和训练方案进行模块化实验。当前为早期研究发布版本，已集成RoboTwin 2.0，支持Wan2.2和Cosmos-Predict2等视频生成模型作为世界模型骨干，覆盖LIBERO等基准测试的训练与部署流程。

## 主要特性
1.  **多类型世界模型骨干**：可复用预训练视频生成模型作为机器人世界模型，如Wan2.2、Cosmos-Predict2
2.  **三类WAM模型家族**：
    - `mot_wam`：多流视频/动作专家混合注意力建模
    - `shared_dit_wam`：共享DiT/注册令牌的视频动作预测
    - `feature_conditioned_action_model`：基于世界模型特征的动作预测
3.  **标准化基准工具链**：内置基准数据集加载、数据预处理、训练与部署脚本
4.  **轻量配置系统**：通过YAML配置文件加载Python数据类，无需依赖Hydra
