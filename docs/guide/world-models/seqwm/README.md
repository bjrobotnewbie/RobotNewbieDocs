# seqwm

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/seqwm/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

官方实现 ICLR'26 论文《通过序列世界模型赋能多机器人协作》

## 项目链接

- GitHub: <https://github.com/zhaozijie2022/seqwm>

## 项目介绍
seqwm是ICLR'26论文《Empowering Multi-Robot Cooperation via Sequential World Models》的官方实现，针对多机器人系统中基于模型的强化学习（MBRL）应用难题，提出了Sequential World Model（SeqWM）框架。该框架通过为每个智能体构建独立的序列结构模型，分解复杂的联合动力学，智能体基于前驱模型的预测进行规划与决策，实现显式意图共享，降低通信复杂度，提升多机器人协作性能，支持预测性适应、角色划分等高级行为。

## 主要特性
1. 采用序列结构的多智能体世界模型，适配多机器人协作场景
2. 支持双灵巧手操作、多四足机器人协作等任务，可扩展至2-5台四足机器人
3. 提供完整的安装流程与训练配置，可通过修改配置文件自定义训练过程
4. 在仿真与真实部署中均表现优于现有SOTA方法
