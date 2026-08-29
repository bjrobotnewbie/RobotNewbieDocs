# FastWAM

Fast-WAM 官方代码库：世界动作模型是否需要测试时的未来想象？

## 项目链接

- GitHub: <https://github.com/yuantianyuan01/FastWAM>
- 项目主页: <https://yuantianyuan01.github.io/FastWAM/>

## 项目介绍
FastWAM是论文《Fast-WAM: Do World Action Models Need Test-time Future Imagination?》的官方代码仓库，支持在LIBERO和RoboTwin数据集上进行世界模型的训练与评估，可实现机器人智能体的决策与控制，支持切换是否使用未来想象进行行动决策。

## 主要特性
1.  **高效推理与训练**：端到端推理速度提升约2倍，NVIDIA H20平台从470ms降至210ms，RTX4090从190ms降至110ms；H20平台训练速度提升约10%。
2.  **多版本数据集支持**：原生兼容LeRobot 2.1和3.0版本数据集，适配大规模数据加载需求。
3.  **灵活可调**：支持开启/关闭测试时未来想象的行动模式，现有模型权重可兼容加速推理流程。
4.  支持两种文本编码模式：缓存文本嵌入与实时T5编码，兼顾效率与便捷性。
