# ros-mcp-server

- 项目链接：https://github.com/robotmcp/ros-mcp-server
- 项目主页：https://robotmcp.ai

## 项目概述

ROS MCP Server 是一个桥接工具，**将大语言模型（Claude、GPT、Gemini 等）连接到 ROS 机器人系统**，实现 AI 模型与机器人的双向通信，无需修改现有机器人源代码。

它基于开放的 [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) 标准构建，可以与任何支持 MCP 的 LLM 客户端配合工作。

### 核心特点

- **无需修改机器人源码**：只需要在现有 ROS 环境中添加 `rosbridge` 节点即可
- **真正双向通信**：LLM 可以控制机器人，也能观察机器人上发生的一切
- **完整上下文访问**：可以发布/订阅话题、调用服务和动作、设置参数、读取传感器数据、实时监控机器人状态
- **深度 ROS 理解**：自动发现可用的话题、服务、动作及其类型，指导 LLM 使用正确的语法，无需手动配置
- **兼容所有 MCP 客户端**：支持 Claude Code、Codex CLI、Gemini CLI、Claude Desktop、ChatGPT、Cursor 等
- **跨 ROS 版本兼容**：同时支持 ROS 2（Jazzy、Humble 等）和 ROS 1

### 工作原理

1. ROS-MCP-Server 发现 ROS 系统中的所有话题、服务、动作
2. 将这些信息暴露给 LLM 作为可用工具
3. LLM 根据用户指令生成 ROS 操作调用
4. ROS-MCP-Server 执行调用并返回结果给 LLM
5. LLM 可以根据执行结果继续推理和生成下一步操作

这是一个非常有趣的项目，让大语言模型能够直接与 ROS 机器人交互，通过自然语言就能控制机器人。
