# RLlib

## 资源简介

RLlib 是由 UC Berkeley RISELab 开发的开源强化学习库，官方定义为"一个用于强化学习的开源库，提供对生产级、高度可扩展和容错的 RL 工作负载的支持，同时为各种行业应用提供简单统一的 API"。

## 官方链接

* 官方文档：<https://docs.ray.io/en/latest/rllib/>
* GitHub仓库：<https://github.com/ray-project/ray>
* Ray官网：<https://www.ray.io/>

## 主要特点

* **生产级支持**：支持大规模、高度可扩展和容错的 RL 工作负载
* **统一 API**：简单统一的接口适用于多种行业应用
* **多智能体支持**：原生支持多智能体强化学习
* **离线学习**：支持从历史离线数据中学习
* **外部模拟器集成**：支持与外部连接的模拟器配合使用
* **丰富的算法库**：涵盖主流强化学习算法

## 支持的算法

| 类别 | 算法 |
|------|------|
| **On-Policy** | PPO (Proximal Policy Optimization) |
| **Off-Policy** | SAC (Soft Actor Critic)、DQN/Rainbow |
| **高吞吐量架构** | APPO、IMPALA |
| **Model-based** | DreamerV3 |
| **Offline RL & 模仿学习** | BC、CQL、MARWIL |

## 行业应用

RLlib 已在多个行业领域得到实际应用：

* 游戏（Game）
* 机器人（Robotics）
* 金融（Finance）
* 气候与工业控制（Climate and Industrial Control）
* 制造业与物流（Manufacturing and Logistics）
* 汽车（Automobile）
* 船舰设计（Boat Design）

## 核心功能

* 多 GPU、多节点分布式训练
* 灵活的环境配置
* 自定义算法和策略
* 在线学习和实时决策
* 丰富的评估工具
* 与 Ray 生态系统无缝集成
