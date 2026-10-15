# oumi

轻松微调（SFT/RL）、评估并部署 Qwen、Gemma 或任何开放式的代理 LLM/VLM！

## 项目链接

- GitHub: <https://github.com/oumi-ai/oumi>
- 项目主页: <https://oumi.ai>

## 项目介绍
oumi是一个端到端的开源工具栈，用于轻松对Qwen、Gemma等各类开源智能体大语言模型（LLM）、多模态大语言模型（VLM）进行微调、评估与部署，助力构建先进的基础模型。

## 主要特性
1. 支持SFT、RL等多种微调方式，近期版本新增工具调用SFT、支持工具使用的GRPO强化学习等功能；
2. 提供模型评估能力，内置多标准`RubricJudge`评估工具；
3. 支持模型部署，提供`oumi deploy` CLI可部署至专用推理端点，还支持与Claude、Cursor等工具集成；
4. 兼容多种主流模型，包括Qwen3.5、Gemma 4等模型家族；
5. 具备工具环境支持，涵盖模拟环境、查询环境、数据库环境，还支持智能体数据合成功能。
