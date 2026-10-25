# dreamerv3

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/dreamerv3/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

通过世界模型掌握多样化领域

## 项目链接

- GitHub: <https://github.com/danijar/dreamerv3>
- 项目主页: <https://danijar.com/dreamerv3>

## 项目介绍
dreamerv3是DreamerV3算法的复现实现，该算法是一种可扩展、通用的强化学习（RL）方法，核心是从经验中学习世界模型，通过想象轨迹训练actor-critic策略，能在固定超参数下掌握多种应用场景，性能优于专用方法，可减少RL应用所需的专业知识和计算资源。项目支持Linux、Mac系统，要求Python 3.11+，基于JAX框架实现。

## 主要特性
1. 通用性强：固定超参数即可适配多种领域，无需针对特定任务调参
2. 扩展性好：模型规模增大可同步提升最终性能和数据效率，增加梯度步数也能进一步提升数据效率
3. 易用性高：提供Docker部署方式，支持命令行覆盖配置项，内置debug配置可快速调试
4. 结果可视化：支持通过scope工具查看训练结果，同时将标量指标以JSONL格式存储
