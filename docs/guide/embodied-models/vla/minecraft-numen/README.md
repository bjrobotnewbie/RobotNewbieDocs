# minecraft-numen

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/minecraft-numen/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Numen 是一个运行在 Minecraft 内部的具身智能体。它以模组的形式存在于游戏中，持续探索 Minecraft 世界，自主做出决策，并执行操作以完成任务。

## 项目链接

- GitHub: <https://github.com/Dwinovo/minecraft-numen>
- 项目主页: <https://numen.dwinovo.cn>
- 中文文档: https://github.com/dwinovo/minecraft-numen/blob/main/README_CN.md

## 项目介绍
Numen（言出法随）是一款运行在Minecraft中的具身智能体模组，可在游戏内自主探索世界、决策并完成任务。支持多种Minecraft版本及加载器，原生兼容OpenAI、Anthropic接口，也可作为MCP服务器由外部智能体驱动。

## 主要特性
- 支持自然语言交互，可召唤自定义智能体，配置人设、皮肤、语音功能
- 具备群聊功能，支持多智能体协同交互
- 分层架构设计，底层为Minecraft游戏环境，中间层提供Lua/Java原子动作API，上层由大语言模型组合动作完成任务
- 支持插件扩展，开发者可接入其他模组功能，提供官方插件参考模板
- 提供快捷操作按键，支持语音输入、多智能体切换等便捷功能
