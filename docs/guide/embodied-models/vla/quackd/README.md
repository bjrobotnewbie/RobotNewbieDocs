# quackd

🦆🧠 为您的小型机器人赋予大脑。告诉您自己构建的 Microduck、Open Duck Mini、Reachy Mini、LeRobot 手臂或任何 ROS 基座，您想让它做什么，只需使用人类语言。LLM（如 Claude、OpenAI、Gemini、Grok，或通过 Ollama、vLLM 或 llama.cpp 运行的本地模型）利用其已有的技能。支持模拟器、.duck 任务文件、MCP、跨运行记忆以及 flock 模式。

## 项目链接

- GitHub: <https://github.com/rokbenko/quackd>
- 项目主页: <https://pypi.org/project/quackd/>

## 项目介绍
quackd是一款面向小型机器人的AI大脑守护进程，支持Microduck、Open Duck Mini、Reachy Mini、LeRobot机械臂以及任意ROS机器人底盘。用户可以通过自然语言向机器人下达任务目标，借助Claude、OpenAI、Gemini、Grok等第三方大模型，或是通过Ollama、vLLM、llama.cpp部署的本地大模型，让机器人自主规划执行步骤。
项目支持仿真环境、.duck格式任务文件、多回合记忆以及多机器人协同（flocks）功能，兼容Python 3.11+，采用Apache 2.0开源协议。

## 主要特性
1.  支持多种主流大模型与本地部署方案
2.  适配多款开源小型机器人与ROS机器人底盘
3.  提供.duck任务文件格式与多会话记忆功能
4.  内置模型上下文协议（MCP）支持
5.  支持仿真环境与多机器人集群协同
