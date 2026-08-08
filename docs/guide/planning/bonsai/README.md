# bonsai

Bonsai 是一个用 Rust 实现的行为树库，并提供 Python 绑定，用于构建模块化、响应式的确定性 AI 行为逻辑。

## 项目链接

- GitHub: <https://github.com/Sollimann/bonsai>

## 项目概述

Bonsai 是一个行为树（Behavior Tree）实现库，主要用 Rust 编写，同时通过 `bonsai-bt` 提供 Python 包。行为树常用于游戏 AI、机器人任务控制和自动化系统，它通过树状结构组织条件、动作和控制节点，让复杂行为能够以模块化、可组合、可响应环境变化的方式表达。

项目 README 重点介绍了行为树的基础概念和常见控制结构，例如 Sequence、Select、If、Invert、While 等节点。这些节点可用于描述“先执行 A 再执行 B”“A 失败后尝试 B”“条件满足时执行某行为”等逻辑，比直接写大量状态机分支更易维护，也更适合复杂任务组合。

Bonsai 适合需要在 Rust 或 Python 中构建确定性 AI 决策逻辑的开发者使用。它可以用于机器人任务编排、游戏角色行为、仿真智能体控制和教学示例。项目还提供概念文档、示例、开发指南以及 crates.io / PyPI 安装方式，便于在不同语言环境中集成。
