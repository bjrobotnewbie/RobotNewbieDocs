# MO-Gymnasium

多目标 Gymnasium 环境用于强化学习

## 项目链接

- GitHub: <https://github.com/Farama-Foundation/MO-Gymnasium>
- 项目主页: <http://mo-gymnasium.farama.org/>

## 项目概述

## 项目介绍
MO-Gymnasium是一款开源Python库，用于开发和对比多目标强化学习（MORL）算法。它提供了标准API来实现学习算法与环境的交互，同时内置了符合Gymnasium API规范的多目标环境，环境返回的奖励为numpy数组形式的向量奖励。官方文档地址为mo-gymnasium.farama.org，同时配有官方Discord开发协作社区。

## 主要特性
1.  兼容Gymnasium标准API，使用门槛低
2.  内置多组MORL经典研究环境，以及经典环境（如MuJoCo）的多目标改造版本
3.  支持通过pip快速安装，可按需安装对应环境依赖包
4.  提供奖励标量化包装器，可灵活将向量奖励转换为标量奖励进行训练
