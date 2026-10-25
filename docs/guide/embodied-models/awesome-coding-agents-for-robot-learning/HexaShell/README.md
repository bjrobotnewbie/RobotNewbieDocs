# HexaShell

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/awesome-coding-agents-for-robot-learning/HexaShell/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

HexaShell: 一个薄层框架，其中编码代理从 RGB 图像驱动机器人并编写自己的工具；包含用于 42 个 RoboDojo 任务的冻结工具。

## 项目链接

- GitHub: <https://github.com/HexaFuture/HexaShell>

## 项目介绍
HexaShell是一款用于探索视觉语言模型（VLM）智能体作为机器人编码智能体极限的轻量级框架，支持ROS相关机器人控制，适配RoboDojo平台的双机械臂ARX X5机器人，基于Isaac Sim仿真环境运行。该框架以RGB图像、相机标定数据及单页任务手册为输入，通过编码智能体驱动机器人完成任务，核心是将机器人失败尝试转化为可复用的工具，在RoboDojo官方评估中取得46.9%的任务成功率、53.2的进度评分，登顶RoboDojo排行榜。

## 主要特性
1. 适配RoboDojo全部42项任务，采用统一接口，无需针对单任务定制工具或指令；
2. 支持失败驱动的工具迭代：失败尝试后，同模型的辅助智能体可分析失败原因，生成或修复带单元测试的工具，平均修复时长6.3分钟；
3. 采用三角测量替代深度感知，通过多视角相机（头部相机+腕部相机）的像素射线交汇定位目标，无需依赖深度数据；
4. 开源提供RoboDojo公开任务的共享配置、工具接口及已冻结的工具集合。
