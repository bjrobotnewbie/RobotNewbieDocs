# cyclotron

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/leisaac/cyclotron/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 Isaac Lab 构建的官方强化学习训练框架，专为 Asimov  humanoid 机器人设计。

## 项目链接

- GitHub: <https://github.com/menloresearch/cyclotron>

## 项目介绍
cyclotron是Menlo Research开发的Asimov 1人形机器人官方强化学习训练框架，基于Isaac Lab构建，用于训练和评估机器人的运动策略，支持仿真环境训练后部署到真实机器人，实现仿真到真实（sim2real）的迁移。

## 主要特性
1. 支持PPO、对抗运动先验（AMP）两种强化学习算法训练Asimov 1的运动策略
2. 提供快速安装脚本，可自动配置基于uv的运行环境，集成Isaac Lab及asimov-1子模块
3. 支持快速测试、单GPU/多GPU训练模式，可通过参数调整环境数量、训练迭代次数等
4. 训练过程支持记录回放视频，自动生成恢复训练的指令，方便从断点继续训练
5. 适配Ubuntu 22.04+（x86_64）系统及兼容NVIDIA驱动，针对不同GPU提供内存优化方案

使用场景：Asimov 1人形机器人的运动策略开发、仿真训练与真实部署，适用于强化学习机器人研究与开发场景。
