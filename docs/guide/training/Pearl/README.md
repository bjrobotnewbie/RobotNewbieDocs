# Pearl

由Meta应用强化学习团队打造的生产可用的强化学习AI智能体库

## 项目链接

- GitHub: <https://github.com/facebookresearch/Pearl>

## 项目介绍
Pearl是Meta应用强化学习团队开源的生产就绪型强化学习AI智能体库，可帮助研究者和开发者构建以长期累计反馈为优先、可适配部分可观测、稀疏反馈、高随机性复杂生产环境的强化学习智能体。项目已在NeurIPS 2023亮相，采用MIT开源协议，官方提供了文档、论文及演示幻灯片。

## 主要特性
1.  支持生产级强化学习智能体开发，适配复杂真实生产场景
2.  支持组件序列化，可通过PyTorch的state_dict机制保存、加载智能体及PolicyLearner、ExplorationModule等子组件状态
3.  内置智能体状态对比校验方法，保障部署一致性
