# Spotter

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/Spotter/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

官方代码库：让具身模型引领，让视觉语言模型辅助

## 项目链接

- GitHub: <https://github.com/zqc3117/Spotter>
- 项目主页: <https://zqc3117.github.io/Spotter/>

## 项目介绍
Spotter是一个具身智能框架，核心是在冻结的具身模型（System 1）与视觉语言模型（VLM，System 2）之间添加轻量干预层，让具身模型主导执行，本地并行运行的VLM仅在确认错误时介入修正，无需VLM全程规划，可使用本地部署的开源Qwen模型，无需特权信息，支持在RoboCasa仿真环境及真实Franka Research 3机器人上完成任务。

## 主要特性
- 采用“具身模型主导+VLM仅纠错”的架构，降低VLM工作复杂度，适配本地开源模型部署
- 支持仿真与真实机器人场景，提供模型检查点及快速上手指南
- 遵循MIT协议，可通过GitHub获取代码并支持项目star鼓励
