# OpenEnv

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/agent-sandbox/OpenEnv/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

RL 训练后环境接口库

## 项目链接

- GitHub: <https://github.com/openenv/OpenEnv>
- 项目主页: <https://huggingface.co/docs/openenv/index>

## 项目介绍
OpenEnv是一个用于智能体强化学习（RL）的端到端框架，提供Gymnasium风格的简单API，支持创建、部署和使用隔离的执行环境，可用于RL训练后的环境交互，适配多种主流RL框架。

## 主要特性
- 统一API：提供`reset()`、`step()`、`state()`等接口，支持同步/异步模式，通过WebSocket通信；
- 隔离部署：环境以Docker镜像形式运行，可本地部署、云沙箱部署或作为Hugging Face Space部署；
- 丰富环境库：包含40+种可用环境，覆盖游戏、代码沙箱、浏览器、金融、模拟器等场景；
- 多框架适配：支持TRL、Unsloth、SkyRL等多种训练框架；
- 代码智能体训练：通过Harbor集成运行多种代码智能体工具链，捕获RL所需的精确token；
- 工具服务：MCP环境可通过`/mcp`向智能体暴露工具，生产模式与训练模式适配不同接口；
- 内置评估与奖励：可通过rubrics组合奖励，支持Inspect AI评估。
