# OpenTau

Tensor 的 VLA 训练基础设施：基于 PyTorch 的机器人学应用

## 项目链接

- GitHub: <https://github.com/TensorAuto/OpenTau>
- 项目主页: <https://opentau.readthedocs.io/>

## 项目概述

## 项目介绍
OpenTau是Tensor开源的PyTorch视觉语言动作(VLA)模型训练工具链，面向真实世界机器人场景，旨在让VLA模型训练具备可复现性、易用性与可扩展性。VLA是具身AI的主流方案，可应用于自动驾驶、机器人操作与导航等领域，该项目致力于推动机器人学习领域的开源知识共享与科研进展。

## 主要特性
1.  支持在异构数据集的可调混合配比上进行联合训练
2.  实现离散动作机制，可加速VLM在π0.5场景下的收敛
3.  支持VLM主干网络与动作专家模块之间的知识隔离
4.  在VLM中加入Dropout机制以降低过拟合风险
