# concordia

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/concordia/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

一个用于生成式社会模拟的库

## 项目链接

- GitHub: <https://github.com/google-deepmind/concordia>

## 项目介绍
Concordia是一个用于构建和运行生成式智能体社交模拟的Python库，可在实体化的物理、社会或数字环境中模拟实体间的交互。它采用类似桌面角色扮演游戏的交互模式，由名为**Game Master（GM）**的特殊实体模拟交互环境，参与实体用自然语言描述行动意图，GM会将其转化为合理的模拟结果。

该库可应用于社会科学研究、AI安全伦理、认知神经科学、经济学、个性化合成数据生成、真实服务模拟测试等场景，需要调用标准大语言模型API，也可集成外部应用服务。

## 主要特性
1.  采用模块化架构，围绕**实体**、**组件**、**引擎**三个核心概念构建
2.  内置核心组件库，支持自定义组件并可加入contrib目录共享
3.  提供预制的通用智能体和GM模板
4.  支持复杂行为通过可复用的简单模块组合实现
