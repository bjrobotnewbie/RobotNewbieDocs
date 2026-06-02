# ReAct (Reasoning + Acting)

ReAct 是一种将推理和行动结合的范式，让大语言模型在解决任务时交替进行思考推理和执行动作，从而实现复杂任务的自主完成。它是 LLM Agent 最经典的架构之一，被广泛应用于各类智能体系统。

## 简介

ReAct（Reasoning + Acting）是 Google Research 在 2022 年提出的方法，通过让 LLM 生成自然语言的推理轨迹（Thought），然后基于推理执行具体的动作（Action），并观察动作结果（Observation），循环这个过程直到达成目标。

## 核心概念

### 基本循环

```
思考 (Thought) → 动作 (Action) → 观察 (Observation) → 思考...
```

### 核心组件

| 组件 | 说明 | 示例 |
|------|------|------|
| **Thought** | 推理过程，解释当前的思考 | "我需要先搜索这个概念的定义" |
| **Action** | 要执行的具体动作，格式通常为 `Action[参数]` | `Search[强化学习]` |
| **Observation** | 动作执行后的结果，作为新的上下文 | "强化学习是机器学习的一个分支..." |
| **Finish** | 任务完成，给出最终答案 | `Finish[答案...]` |

## 核心特性

### 优势
- ✅ 可解释性强，能看到完整推理链
- ✅ 支持工具调用和环境交互
- ✅ 可以处理复杂多步骤任务
- ✅ 易于调试和提示工程优化
- ✅ 适用范围广，扩展性好

### 局限
- ❌ 推理和行动交替速度较慢
- ❌ 可能陷入无限循环或死胡同
- ❌ 对提示工程敏感
- ❌ 长上下文可能导致遗忘
- ❌ 工具调用质量影响最终效果

## 典型实现框架

### LangChain ReAct
- **特点**：最流行的实现，生态丰富
- **项目地址**：https://github.com/langchain-ai/langchain
- **文档**：https://python.langchain.com/docs/modules/agents/agent_types/react
- **功能**：支持多种工具、自定义提示、记忆管理

### LlamaIndex Agent
- **特点**：聚焦 RAG 和文档问答
- **项目地址**：https://github.com/run-llama/llama_index
- **文档**：https://docs.llamaindex.ai/

### AutoGPT
- **特点**：完整的自主智能体实现
- **项目地址**：https://github.com/Significant-Gravitas/AutoGPT
- **功能**：长期记忆、目标分解、多工具支持

### BabyAGI
- **特点**：轻量级任务管理智能体
- **项目地址**：https://github.com/yoheinakajima/babyagi
- **特性**：任务创建、优先级、执行循环

## 应用场景

### 知识问答与研究
- 多跳问答
- 文献调研
- 事实核查
- 信息整合

### 软件开发
- 代码编写与调试
- 文档生成
- 测试用例设计
- 代码审查

### 数据分析
- 数据探索
- 可视化生成
- 报告撰写
- 异常检测

### 机器人任务规划
- 高层任务分解
- 环境感知与决策
- 异常处理与恢复
- 多模态交互

## 快速开始

### 基础 ReAct 提示模板

```text
你是一个智能助手，可以使用以下工具来完成任务：

{tools}

使用以下格式：

Question: 用户的问题
Thought: 你应该思考要做什么
Action: 要执行的动作，应该是 [{tool_names}] 中的一个
Action Input: 动作的输入
Observation: 动作执行的结果
...（重复 Thought/Action/Action Input/Observation）
Thought: 我现在知道最终答案了
Final Answer: 最终答案

开始！

Question: {input}
{agent_scratchpad}
```

### LangChain 实现示例

```python
from langchain.agents import AgentType, initialize_agent
from langchain.llms import OpenAI
from langchain.tools import Tool

# 1. 定义工具
def search(query: str) -> str:
    """搜索信息"""
    return f"搜索结果: {query} 的相关信息..."

tools = [
    Tool(
        name="Search",
        func=search,
        description="用于搜索信息"
    )
]

# 2. 初始化 LLM
llm = OpenAI(temperature=0)

# 3. 创建 ReAct Agent
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    verbose=True
)

# 4. 运行任务
result = agent.run("解释什么是强化学习？")
print(result)
```

### 自定义 ReAct 循环实现

```python
import openai

def run_react_task(question, max_steps=5):
    messages = [
        {"role": "system", "content": """
你是一个 ReAct 智能体。按照以下格式回答：

Thought: 你的思考
Action: 动作名称[参数]
Observation: 动作结果

当你知道答案时，直接说：
Final Answer: 答案

可用动作：
- Search[query]: 搜索信息
- Calculate[expression]: 计算数学表达式
"""},
        {"role": "user", "content": question}
    ]
    
    for step in range(max_steps):
        response = openai.ChatCompletion.create(
            model="gpt-3.5-turbo",
            messages=messages
        )
        
        thought = response.choices[0].message.content
        print(f"Step {step + 1}:")
        print(f"  {thought}")
        
        if "Final Answer:" in thought:
            break
            
        if "Action:" in thought:
            # 解析并执行动作
            action_line = [line for line in thought.split('\n') if 'Action:' in line][0]
            action = action_line.split('Action:')[1].strip()
            
            # 执行动作获取观察结果
            observation = execute_action(action)
            print(f"  Observation: {observation}")
            
            messages.append({"role": "assistant", "content": thought})
            messages.append({"role": "user", "content": f"Observation: {observation}"})
```

## 设计模式

### 1. 工具设计模式

```python
# 工具应该有清晰的输入输出定义
class BaseTool:
    name: str
    description: str
    
    def run(self, input: str) -> str:
        """执行工具逻辑"""
        pass

# 工具注册机制
tool_registry = {
    "Search": SearchTool(),
    "Calculator": CalculatorTool(),
    "CodeExecutor": CodeExecutorTool()
}
```

### 2. 记忆管理模式

```python
class Memory:
    def __init__(self):
        self.short_term = []  # 当前会话
        self.long_term = []   # 历史知识
        
    def add(self, observation):
        self.short_term.append(observation)
        
    def get_context(self):
        return "\n".join(self.short_term[-5:])  # 最近5条
```

### 3. 错误恢复模式

```python
# 重试机制
max_retries = 3
for retry in range(max_retries):
    try:
        result = agent.run(task)
        break
    except Exception as e:
        if retry < max_retries - 1:
            agent.reflection(f"上次执行失败: {e}，请重试")
```

## 最佳实践

### 1. 提示工程
- **清晰的格式指令**：明确指定输出格式
- **工具描述准确**：工具功能描述要精确
- **示例展示**：提供少量示例帮助理解
- **约束条件**：明确限制和边界

### 2. 工具设计
- **单一职责**：每个工具只做一件事
- **输入验证**：验证工具输入格式
- **错误处理**：优雅处理工具执行失败
- **返回格式**：统一的返回格式

### 3. 性能优化
- **限制步骤数**：防止无限循环
- **上下文压缩**：精简历史信息
- **并行执行**：支持独立动作并行
- **缓存机制**：缓存频繁查询结果

### 4. 调试技巧
- **详细日志**：记录每个思考步骤
- **可视化**：图形化展示推理链
- **断点调试**：支持人工干预
- **指标监控**：成功率、步骤数、耗时

## 高级扩展

### 1. 反思机制
在标准 ReAct 基础上增加反思步骤：
```
Thought → Action → Observation → Reflection → Thought...
```

### 2. 规划器-执行器分离
```
Planner: 生成子任务计划
Executor: 执行每个子任务
Monitor: 监控执行状态
```

### 3. 多智能体协作
```
Planner Agent → 规划任务
Executor Agent → 执行动作
Critic Agent → 评估结果
```

## ReAct 变种对比

| 方法 | 特点 | 适用场景 |
|------|------|---------|
| **基础 ReAct** | 简单直接 | 大多数场景 |
| **ReAct + Reflection** | 增加反思 | 复杂推理任务 |
| **ReWOO** | 规划执行分离 | 长任务规划 |
| **Plan-and-Execute** | 先规划后执行 | 多步骤复杂任务 |

## 相关资源

- [ReAct 论文](https://arxiv.org/abs/2210.03629) - ReAct: Synergizing Reasoning and Acting in Language Models
- [LangChain ReAct 文档](https://python.langchain.com/docs/modules/agents/agent_types/react)
- [ReAct 官方实现](https://github.com/ysymyth/ReAct) - GitHub 仓库
- [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT) - 自主智能体实现
- [BabyAGI](https://github.com/yoheinakajima/babyagi) - 任务驱动智能体
- [OpenAI 函数调用](https://platform.openai.com/docs/guides/function-calling) - 官方工具调用方案
