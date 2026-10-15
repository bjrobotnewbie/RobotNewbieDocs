# Semantic-Framework

InsightOS Semantic 是由具识智能（Jushi Intelligence）构建的具身 AI 语义代理系统。它语义连接机器人的身体、环境、任务、技能和操作经验；将自然语言需求转化为机器人可执行的任务；并实现从理解、规划到执行的完整闭环。

## 项目链接

- GitHub: <https://github.com/insightos-community/Semantic-Framework>
- 项目主页: <https://semantic.insightos.cn/>

## 项目介绍
Semantic-Framework是具识智能推出的InsightOS Semantic语义智能体系统的开源实现，专为具身AI场景设计，核心是通过语义连接机器人本体、环境、任务、技能与操作经验，将自然语言需求转化为机器人可执行任务，实现“理解-规划-执行-迭代”的完整闭环，支持仓库拣选配送、拆码垛、多机器人生产线、定时巡检等场景，适配人形机器人、四足机器人、机械臂、移动机器人等多种机器人本体。

## 主要特性
- 系统核心组件包含管理项目、任务、注册表与运行时协调的semantic-server，连接机器人执行环境的semantic-pilot，以及提供配置与运行时管理的semantic CLI
- 基于CloudWeGo的Go语言LLM应用开发框架Eino构建，智能体层采用Eino的Agent开发工具包（ADK）、模型接口与工具编排能力，集成EinoExt的模型提供商能力
- 解决机器人从演示到实际作业面临的意图理解难题，适配真实工业场景的机器人应用需求，配套Studio、机器人技能、仿真等生态组件（维护于独立仓库）
