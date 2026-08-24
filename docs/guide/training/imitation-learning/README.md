# imitation-learning

模仿学习算法

## 项目链接

- GitHub: <https://github.com/Kaixhin/imitation-learning>

## 项目概述

## 项目介绍
本项目是一个深度模仿学习算法集合，基于SAC作为基础强化学习（RL）算法，实现了AdRIL、DRIL（带dropout版本）、GAIL（即DAC/SAM）、GMMIL、PWIL（nofill版本）、RED等多种模仿学习算法，同时支持行为克隆（BC）预训练、仅状态模仿学习、吸收态标记、专家与智能体数据混合训练、BC辅助损失等通用配置。项目已在Gym MuJoCo环境和D4RL "expert-v2"数据集上进行了基准测试。

## 主要特性
1.  集成多款主流模仿学习算法，覆盖多种技术路线
2.  提供丰富的通用可调参数，支持自定义训练流程
3.  各算法均支持专属配置项，如AdRIL的平衡采样、DRIL的分位数截断、GAIL的奖励塑形与多种损失函数、PWIL与RED的带宽参数等
4.  支持基于Gym MuJoCo环境与D4RL数据集的标准基准测试
