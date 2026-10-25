# genedynamics

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/genedynamics/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

生成动力学：面向机器人规划、控制与学习。

## 项目链接

- GitHub: <https://github.com/hhhhzl/genedynamics>
- 项目主页: <https://hhhhzl.github.io/generative-dynamics/>

## 项目介绍
genedynamics（GenerativeDynamics）是一个面向机器人学规划、控制与学习的模块化技术栈，核心是将流形上的生成模型、流形几何与机器人学习相结合，支持在Python中直接使用组件或通过配置运行完整实验。项目基于JAX计算框架，兼容Python 3.10-3.12，当前为0.1.0 alpha版本，采用MIT许可协议。

## 主要特性
1. 模块化设计，支持算法替换、控制器组合与机器人扩展，可连接规划到闭环控制；
2. 内置机器人学习功能，支持PPO/SAC策略训练、可复用检查点及MGA的PPO horizon先验；
3. 提供规划、环境与约束目录，支持GPU、Docker快速启动，包含批量约束示例、Python规划示例等；
4. 适配真实机器人与仿真场景，涵盖MDOC、MD-COAS、2GO、MGA等演示场景。
