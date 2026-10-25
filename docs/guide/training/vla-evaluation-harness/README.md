# vla-evaluation-harness

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/vla-evaluation-harness/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

任何 VLA 模型在任意机器人仿真基准上的评估框架。

## 项目链接

- GitHub: <https://github.com/allenai/vla-evaluation-harness>
- 项目主页: <https://allenai.github.io/vla-evaluation-harness/>
- [robomme_policy_learning（MME-VLA-Suite）](/guide/training/vla-evaluation-harness/robomme_policy_learning/README)
## 项目介绍
本项目是vla-evaluation-harness，是一个通用的评估框架，可以在任意机器人仿真基准测试中评估任意视觉语言动作（VLA）模型，由艾伦人工智能研究院开发。项目支持通过PyPI安装、Docker部署，兼容Python 3.8+，并通过了CI自动化测试。

## 主要特性
1.  **多基准支持**：已兼容LIBERO、SimplerEnv、CALVIN、LIBERO-Plus、RoboMME、MolmoSpaces-Bench等多款机器人仿真基准，部分基准处于适配中
2.  **通用适配能力**：可以灵活对接不同的VLA模型和机器人仿真测试集
3.  提供标准化的评估流程，简化VLA模型的性能测试工作。
