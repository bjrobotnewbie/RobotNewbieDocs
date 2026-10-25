# tdmpc2

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/tdmpc2/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

TD-MPC2：可扩展、鲁棒的连续控制世界模型代码

## 项目链接

- GitHub: <https://github.com/nicklashansen/tdmpc2>
- 项目主页: <https://www.tdmpc2.com>

## 项目介绍
tdmpc2是论文《TD-MPC2: Scalable, Robust World Models for Continuous Control》的官方实现，是一种可扩展、鲁棒的基于模型的强化学习（RL）算法，支持单任务在线RL与多任务离线RL的训练和评估，适用于连续控制任务。

## 主要特性
1. 泛化能力强：仅需一组超参数即可在104个跨领域连续控制任务中取得优异表现，还可训练3.17亿参数的单智能体完成80个跨领域、不同形态及动作空间的任务；
2. 功能丰富：新增支持带终止条件的 episodic RL 任务，默认关闭以保证结果可复现；
3. 资源开放：提供300+模型检查点（含12个多任务模型），覆盖DMControl、Meta-World等4类任务领域，同时开放30任务与80任务训练数据集；
4. 观测支持：兼容状态与像素观测；
5. 部署便捷：提供Dockerfile用于快速安装，单任务在线RL需GPU及至少12GB内存，多任务离线RL需128GB内存，大模型训练需24GB以上GPU内存。
