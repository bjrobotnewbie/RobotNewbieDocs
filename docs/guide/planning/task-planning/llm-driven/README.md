# LLM 驱动的任务规划

LLM 驱动的任务规划利用大语言模型的语义理解能力、常识知识和推理能力，直接从自然语言指令生成任务计划。这是当前机器人智能领域最活跃的研究方向之一，显著提升了机器人的泛化能力和人机交互体验。

## 分类总览

| 范式 | 核心思想 | 代表工作 | 优势 | 局限性 |
|------|---------|---------|------|--------|
| **ReAct** | 思考-行动-观察循环 | Google ReAct | 可解释性强、工具使用好 | 需要多轮交互 |
| **Reflexion** | 执行-评估-反思迭代 | Noah Shinn 等 | 从失败中学习、成功率高 | 需要多次尝试 |
| **AutoGen** | 多智能体协作 | Microsoft AutoGen | 分工明确、复杂任务处理好 | 对话可能冗长 |

---

## 范式详解

### 1. [ReAct (Reasoning + Acting)](/guide/planning/task-planning/llm-driven/react/README.md)

ReAct 是最经典的 LLM Agent 架构之一，通过交替进行推理和行动来解决复杂任务。

**核心循环：**
```
用户问题
  ↓
思考 (Thought)：分析当前状态，决定下一步做什么
  ↓
行动 (Action)：调用工具/函数，执行具体操作
  ↓
观察 (Observation)：获取行动结果
  ↓
循环回到思考，直到任务完成
  ↓
最终答案
```

**典型提示词结构：**
```
你是一个智能助手，按照以下格式回答问题：

Question: 用户的问题
Thought: 你应该思考什么
Action: 要执行的动作，只能是 [Search, Calculate, Code] 中的一个
Action Input: 动作的输入参数
Observation: 动作执行的结果
...（重复 Thought/Action/Action Input/Observation）
Thought: 我现在知道答案了
Final Answer: 最终答案

开始！
```

**主要实现框架：**
- LangChain Agents - 最流行的 ReAct 实现
- LlamaIndex Agents - 聚焦 RAG 场景
- AutoGPT - 自主智能体实现

---

### 2. [Reflexion (反思式规划)](/guide/planning/task-planning/llm-driven/reflexion/README.md)

Reflexion 在 ReAct 的基础上增加了反思机制，让智能体能够从失败中学习并改进策略。

**核心流程：**
```
第 N 次尝试
  ↓
执行任务 (ReAct 模式)
  ↓
评估结果：成功/失败？
  ↓ 失败
生成反思：哪里错了？如何改进？
  ↓
第 N+1 次尝试（结合反思经验）
  ↓
直到成功或达到最大尝试次数
```

**评估模块示例：**
```
请评估以下任务执行结果：

任务：编写一个快速排序算法
执行结果：[代码内容]

评估标准：
1. 正确性：代码是否能正确运行？
2. 完整性：是否包含测试用例？
3. 可读性：注释是否清晰？

请给出评分和具体反馈。
```

**记忆机制：**
```
长期记忆库
  ├─ 成功经验：有效的策略和方法
  ├─ 失败教训：避免重复的错误
  └─ 模式总结：通用的问题解决模式
```

---

### 3. [AutoGen (多智能体协作)](/guide/planning/task-planning/llm-driven/autogen/README.md)

AutoGen 通过多个专门化的智能体分工协作来处理复杂任务，每个智能体扮演不同角色。

**典型团队配置：**
```
用户
  ↓
产品经理 Agent：需求分析、任务规划
  ↓
架构师 Agent：技术方案设计
  ↓
程序员 Agent：代码编写
  ↓
测试工程师 Agent：测试验证、反馈问题
  ↓
代码执行 Agent：实际运行、输出结果
```

**对话模式：**
- **双人对话**：两个智能体一对一交互（如用户代理 + 助手）
- **群聊模式**：多个智能体自由讨论，组长协调流程
- **顺序对话**：按预定义流水线传递任务
- **动态选择**：根据上下文选择下一个发言者

**核心智能体类型：**
- **AssistantAgent**：通用助手，代码生成、问题解答
- **UserProxyAgent**：代表用户，执行代码、获取人类输入
- **ConversableAgent**：可自定义的基础对话智能体
- **GroupChatManager**：群聊管理者，协调对话流程

---

## 技术选型对比

| 维度 | ReAct | Reflexion | AutoGen |
|------|-------|-----------|---------|
| **实现复杂度** | 简单 | 中等 | 复杂 |
| **任务复杂度** | 中等 | 复杂 | 非常复杂 |
| **执行速度** | 快 | 慢（多次尝试） | 中等 |
| **成功率** | 中等 | 高 | 很高 |
| **可解释性** | 高 | 高 | 中等 |
| **资源消耗** | 低 | 高 | 很高 |
| **调试难度** | 低 | 中等 | 高 |

---

## 混合架构推荐

### 推荐架构：LLM + 传统规划混合

```
用户自然语言指令
  ↓
LLM 理解与分解层（ReAct/AutoGen）
  ├─ 解析用户意图
  ├─ 分解为可执行子任务
  └─ 处理异常和歧义
  ↓
传统规划层（行为树/HTN）
  ├─ 任务执行流编排
  ├─ 状态管理
  └─ 异常处理逻辑
  ↓
运动规划层（MoveIt/OMPL）
  ├─ 碰撞检测
  ├─ 轨迹生成
  └─ 运动约束
  ↓
机器人执行控制
```

### 优势：
- ✅ LLM 处理开放域指令，泛化能力强
- ✅ 传统规划保证执行确定性和安全性
- ✅ 层次化设计，各层职责清晰
- ✅ 便于调试和维护

---

## 挑战与发展方向

### 当前挑战
1. **幻觉问题**：LLM 可能生成不合理的规划
2. **长上下文**：复杂任务历史信息丢失
3. **成本问题**：多轮推理 Token 消耗大
4. **实时性**：推理延迟影响机器人响应
5. **验证困难**：如何保证生成规划的安全性

### 发展趋势
1. **工具使用增强**：更丰富的机器人专用工具
2. **世界模型集成**：结合仿真进行预验证
3. **反馈学习**：从执行结果中持续改进
4. **多模态规划**：结合视觉、力觉等感知信息
5. **安全验证**：形式化方法验证规划安全性

---

## 相关资源

### ReAct
- [ReAct 论文](https://arxiv.org/abs/2210.03629)
- [LangChain Agents 文档](https://python.langchain.com/docs/modules/agents/)
- [官方实现代码](https://github.com/ysymyth/ReAct)

### Reflexion
- [Reflexion 论文](https://arxiv.org/abs/2303.11366)
- [官方 GitHub 仓库](https://github.com/noahshinn/reflexion)
- [LangGraph 文档](https://langchain-ai.github.io/langgraph/)

### AutoGen
- [AutoGen 官方网站](https://microsoft.github.io/autogen/)
- [GitHub 仓库](https://github.com/microsoft/autogen)
- [示例代码库](https://github.com/microsoft/autogen/tree/main/samples)

### 综述与教程
- [LLM Agent 综述](https://arxiv.org/abs/2308.11432)
- [Planning with Large Language Models](https://arxiv.org/abs/2305.05713)
- [机器人 LLM 规划教程](https://github.com/robotics-lm/awesome-robotics-llm)
