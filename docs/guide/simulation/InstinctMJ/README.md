# InstinctMJ

适用于人形机器人RL与Project-Instinct工作流的InstinctLab mjlab原生移植版本

## 项目链接

- GitHub: <https://github.com/project-instinct/InstinctMJ>

## 项目概述

## 项目介绍
InstinctMJ 是 InstinctLab 的 mjlab 原生移植版本，作为 Project-Instinct 的环境端项目，旨在推动人形机器人全身控制的强化学习工业化落地。它基于 mjlab 框架，集成 MuJoCo Warp 模拟器，适配 Python 3.10+，支持 Linux x86_64 和 macOS arm64 平台，可接入 Project-Instinct 的训练工作流。

## 主要特性
1.  **独立开发**：可脱离核心 mjlab 仓库，实现任务开发自闭环
2.  **丰富任务集**：提供人形机器人的行走、模仿、感知、跑酷等多类控制任务
3.  **统一生态**：可直接对接 instinct_rl 完成训练、测试与模型导出流程
4.  **规范日志**：实验日志统一存储在 `logs/instinct_rl/<实验名>/<运行时间戳>/` 目录，符合 Project-Instinct 工作流规范

本项目采用 CC BY-NC 4.0 开源协议，禁止商用。使用时需注意仅适配基于自身关节顺序训练的模型权重，不可直接跨模拟器复用 checkpoint。
