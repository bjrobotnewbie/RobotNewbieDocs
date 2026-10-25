# Kinesis

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/control/Kinesis/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[ICRA 2026] 该论文《基于强化学习的生理上合理运动模仿》的官方实现

## 项目链接

- GitHub: <https://github.com/amathislab/Kinesis>
- 项目主页: <https://doi.org/10.48550/arXiv.2503.14637>

## 项目介绍
Kinesis是ICRA 2026收录论文的官方实现，是一种基于强化学习（RL）的运动模仿框架，用于开发高效可扩展的肌肉控制策略，适用于肌肉骨骼运动控制场景。该框架基于1.8小时的运动数据训练，可实现对未见过轨迹的运动模仿，生成的肌肉活动模式与人类肌电图（EMG）数据高度相关，可用于人类运动控制理论研究。

## 主要特性
1. 支持最多290块肌肉的肌肉骨骼体，具备良好的可扩展性；
2. 采用负挖掘方法学习鲁棒的运动先验，可部署至文本转控制、目标点到达、方向控制、足球点球等下游任务；
3. 2.0版本新增对足球点球、疲劳等场景的支持，配套的Muscle Mimic项目可实现由416块肌肉控制的全身模型。
