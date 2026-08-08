# RoboManipBaselines

一个集成了多种模仿学习方法与机器人操作基准环境的软件框架

## 项目链接

- GitHub: <https://github.com/isri-aist/RoboManipBaselines>
- 项目主页: https://isri-aist.github.io/RoboManipBaselines-ProjectPage/

## 项目概述

## 项目介绍
RoboManipBaselines是一款面向机器人操作任务的软件框架，集成了多种模仿学习方法与基准测试环境，提供易用的策略训练、评估与部署基线方案。支持在MuJoCo仿真环境中快速采集数据、训练模型并部署策略，附带完整的快速上手与安装指南。

## 主要特性
1.  内置多种主流机器人操作策略架构：包括MLP前馈策略、SARNN循环策略、ACT/MT-ACTTransformer动作分块策略、扩散策略、3D点云输入的扩散/流匹配策略、多模态视觉语言策略（如基于PaliGemma的pi0、基于Eagle-2的GR00T）等
2.  提供标准化的机器人操作任务基准环境与快速上手流程
3.  支持从数据采集、模型训练到策略部署的完整操作流程链路
