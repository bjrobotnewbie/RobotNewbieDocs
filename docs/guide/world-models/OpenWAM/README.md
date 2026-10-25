# OpenWAM

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/OpenWAM/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

可扩展的机器人学习中的视频 - 动作世界模型

## 项目链接

- GitHub: <https://github.com/OpenWAM/OpenWAM>
- 项目主页: <https://openwam.github.io/OpenWAM/>

## 项目介绍
OpenWAM是斯坦福大学视觉与学习实验室开发的可扩展机器人学习视频-动作世界模型框架，当前为0.2.0版本，属于Linux平台的alpha级研究软件，支持Python 3.11及3.12，采用AGPL-3.0许可。该框架将模型拓扑、视频/动作条件设置、序列语义、视觉执行与动作解码分离，便于开展受控实验，共享训练器与视觉栈，适用于机器人学习领域的相关研究。

## 主要特性
1. 模块化设计：分离模型拓扑、视频/动作条件设置、序列语义、视觉执行与动作解码，支持受控实验复用训练器与视觉栈
2. 可扩展性：提供扩展SDK，便于二次开发
3. 配套文档：包含快速入门、方法说明、实验运行、迁移指南等完善文档，支持训练与评估流程
4. 实验支持：支持CPU生命周期与合成工件的自包含运行，大规模基准实验可使用独立配置的数据集与检查点
