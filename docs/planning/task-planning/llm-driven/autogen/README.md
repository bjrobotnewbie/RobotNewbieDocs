# AutoGen (多智能体协作规划)

AutoGen 是微软开发的多智能体框架，通过多个专业化智能体的分工协作来完成复杂任务。它提供了灵活的对话模式、代码执行能力、人类交互支持，是当前最成熟的多智能体协作框架之一。

## 简介

AutoGen 是一个开源框架，支持开发可对话、可协作的 LLM 智能体。它的核心思想是通过多个专门化的智能体（如规划者、执行者、批评者、用户代理等）的协作来解决复杂问题，每个智能体扮演不同的角色，通过对话交互共同推进任务完成。

## 核心概念

### 智能体类型

| 智能体 | 角色 | 主要功能 |
|-------|------|---------|
| **AssistantAgent** | 助手 | 代码生成、问题解决、规划建议 |
| **UserProxyAgent** | 用户代理 | 代表用户执行代码、获取输入、提供反馈 |
| **ConversableAgent** | 对话代理 | 可自定义的基础对话智能体 |
| **GroupChatManager** | 组长 | 管理多智能体群聊，协调对话流程 |

### 对话模式

| 模式 | 说明 | 典型应用 |
|------|------|---------|
| **双人对话** | 两个智能体一对一交互 | 代码审查、问题调试 |
| **群聊模式** | 多个智能体自由讨论 | 创意生成、复杂问题协作 |
| **顺序对话** | 按预定义顺序传递 | 流水线任务处理 |
| **动态对话** | 根据上下文动态选择 | 自适应任务处理 |

## 核心特性

### 优势
- ✅ 多智能体协作，分工明确
- ✅ 内置代码执行沙箱
- ✅ 支持人类在回路中
- ✅ 灵活的对话模式
- ✅ 丰富的自定义能力
- ✅ 支持多种 LLM 后端

### 局限
- ❌ 对话流程可能冗长
- ❌ 智能体角色冲突可能导致混乱
- ❌ 群聊模式难以控制
- ❌ 大任务容易偏离目标
- ❌ 调试复杂度高

## 典型应用架构

### 软件开发团队模式

```
用户
 ↓
产品经理 Agent → 需求分析
 ↓
架构师 Agent → 技术方案设计
 ↓
程序员 Agent → 代码编写
 ↓
测试工程师 Agent → 测试与反馈
 ↓
代码执行 Agent → 实际运行
```

### 任务规划协作模式

```
用户需求
 ↓
规划者 Agent → 生成详细任务计划
 ↓
执行者 Agent → 分步执行子任务
 ↓
批评者 Agent → 评估执行结果
 ↓
反思者 Agent → 调整策略改进
```

### 研究团队模式

```
用户问题
 ↓
文献检索 Agent → 收集资料
 ↓
分析 Agent → 整理分析
 ↓
写作 Agent → 撰写报告
 ↓
审稿 Agent → 审查修改
```

## 快速开始

### 基础安装

```bash
pip install pyautogen
```

### 双人协作示例

```python
import autogen

# 配置 LLM
config_list = [
    {
        "model": "gpt-4",
        "api_key": "your_api_key"
    }
]

llm_config = {
    "config_list": config_list,
    "temperature": 0,
}

# 创建用户代理（可以执行代码）
user_proxy = autogen.UserProxyAgent(
    name="User_proxy",
    system_message="你是一个人类用户，可以执行代码并提供反馈。",
    code_execution_config={"work_dir": "coding"},
    human_input_mode="TERMINATE",
    max_consecutive_auto_reply=10,
    is_termination_msg=lambda x: x.get("content", "").rstrip().endswith("TERMINATE"),
)

# 创建助手代理
assistant = autogen.AssistantAgent(
    name="Assistant",
    system_message="你是一个有用的助手。请帮助用户解决问题。当任务完成时，请回复 TERMINATE。",
    llm_config=llm_config,
)

# 开始对话
user_proxy.initiate_chat(
    assistant,
    message="请编写一个 Python 程序，实现快速排序算法并测试。"
)
```

### 多智能体群聊示例

```python
import autogen

config_list = [{"model": "gpt-4", "api_key": "your_api_key"}]
llm_config = {"config_list": config_list}

# 创建多个智能体
planner = autogen.AssistantAgent(
    name="Planner",
    system_message="""你是规划专家。负责分析任务并制定详细的执行计划。
请按照以下格式输出计划：
1. [步骤1]：描述
2. [步骤2]：描述
...
""",
    llm_config=llm_config,
)

executor = autogen.AssistantAgent(
    name="Executor",
    system_message="你是执行者。负责按照规划执行具体的子任务，并输出结果。",
    llm_config=llm_config,
)

critic = autogen.AssistantAgent(
    name="Critic",
    system_message="""你是批评者。负责评估执行者的结果，指出问题和改进建议。
如果结果满意，请说：满意并结束。""",
    llm_config=llm_config,
)

user_proxy = autogen.UserProxyAgent(
    name="User_proxy",
    system_message="人类用户",
    human_input_mode="TERMINATE",
    code_execution_config={"work_dir": "groupchat"},
)

# 创建群聊
groupchat = autogen.GroupChat(
    agents=[user_proxy, planner, executor, critic],
    messages=[],
    max_round=12
)

manager = autogen.GroupChatManager(
    groupchat=groupchat,
    llm_config=llm_config,
)

# 开始任务
user_proxy.initiate_chat(
    manager,
    message="""请规划并实现一个简单的待办事项管理系统。
要求：
1. 支持添加、删除、列出待办
2. 支持标记完成
3. 数据持久化保存
"""
)
```

### 机器人任务规划示例

```python
import autogen

config_list = [{"model": "gpt-4", "api_key": "your_api_key"}]
llm_config = {"config_list": config_list}

# 任务规划智能体
task_planner = autogen.AssistantAgent(
    name="Task_Planner",
    system_message="""你是机器人任务规划专家。负责将高级任务分解为机器人可执行的动作序列。
输出格式：
任务分解：
1. [动作1]：参数说明
2. [动作2]：参数说明
...
""",
    llm_config=llm_config,
)

# 运动规划智能体
motion_planner = autogen.AssistantAgent(
    name="Motion_Planner",
    system_message="""你是运动规划专家。负责将高层动作转换为具体的运动规划指令。
考虑避障、关节限制、运动平滑等因素。""",
    llm_config=llm_config,
)

# 执行监控智能体
exec_monitor = autogen.AssistantAgent(
    name="Execution_Monitor",
    system_message="""你是执行监控专家。负责监控任务执行状态，检测异常并提出恢复策略。
如果检测到失败，给出备选方案。""",
    llm_config=llm_config,
)

# 用户代理
user_proxy = autogen.UserProxyAgent(
    name="Operator",
    human_input_mode="TERMINATE",
)

# 群聊管理
groupchat = autogen.GroupChat(
    agents=[user_proxy, task_planner, motion_planner, exec_monitor],
    messages=[],
    max_round=15
)

manager = autogen.GroupChatManager(
    groupchat=groupchat,
    llm_config=llm_config,
)

# 开始机器人任务
user_proxy.initiate_chat(
    manager,
    message="""请规划机器人取物任务：
目标：从客厅桌子上拿起水杯，送到卧室的床头柜上
约束：避开障碍物，保持杯子水平
"""
)
```

## 设计模式

### 1. 角色分工模式

```python
# 定义明确的角色职责
class Roles:
    PLANNER = "负责整体规划和任务分解"
    EXECUTOR = "负责具体执行"
    CRITIC = "负责质量评估"
    REVIEWER = "负责最终审核"
```

### 2. 状态机模式

```python
class TaskState:
    INIT = "初始化"
    PLANNING = "规划中"
    EXECUTING = "执行中"
    REVIEWING = "审核中"
    COMPLETED = "完成"
    FAILED = "失败"

# 根据状态选择下一个发言的智能体
def state_based_speaker_selection(last_speaker, groupchat):
    current_state = determine_state(groupchat.messages)
    return get_agent_for_state(current_state)
```

### 3. 子任务协调模式

```python
# 主任务分解为子任务，分别处理
def decompose_task(main_task):
    subtasks = planner.decompose(main_task)
    
    for subtask in subtasks:
        # 分配给专门的智能体处理
        result = assign_subtask(subtask, specialized_agent)
        # 收集结果并整合
```

## 最佳实践

### 1. 智能体设计
- **单一职责**：每个智能体只负责一个明确的角色
- **清晰的系统提示**：明确职责、输出格式、边界条件
- **角色差异化**：避免智能体功能重叠
- **终止条件明确**：每个智能体知道何时结束

### 2. 群聊管理
- **限制轮数**：防止无限对话
- **引导发言顺序**：使用自定义发言选择逻辑
- **设定仲裁机制**：处理智能体间的分歧
- **定期总结**：防止话题偏离

### 3. 代码执行安全
- **使用沙箱环境**：隔离执行环境
- **限制执行权限**：最小权限原则
- **审查危险操作**：文件删除、网络请求等
- **超时控制**：防止长时间运行

### 4. 人类交互
- **适当的干预点**：关键决策时引入人类
- **明确的提示**：告诉用户需要做什么
- **提供上下文**：给出足够的背景信息
- **支持中断和恢复**

## 高级扩展

### 1. 工具集成

```python
# 智能体可以调用外部工具
def execute_robot_command(command: str, params: dict) -> str:
    """执行机器人控制命令"""
    # 连接机器人执行系统
    result = robot_controller.execute(command, params)
    return result

# 注册工具给智能体使用
assistant.register_function(
    function_map={
        "move_robot": move_robot,
        "grasp_object": grasp_object,
        "check_obstacle": check_obstacle
    }
)
```

### 2. 记忆系统

```python
# 给智能体增加长期记忆
class MemoryEnabledAgent(autogen.ConversableAgent):
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.long_term_memory = []
        
    def receive(self, message, sender):
        # 存储重要信息到长期记忆
        if self.is_important(message):
            self.long_term_memory.append(message)
        super().receive(message, sender)
        
    def generate_reply(self, messages, sender, config):
        # 在生成回复前检索相关记忆
        relevant_memory = self.retrieve_relevant_memory(messages)
        # 将记忆加入上下文
        return super().generate_reply(
            self.augment_with_memory(messages, relevant_memory),
            sender, config
        )
```

### 3. 学习与适应

```python
# 智能体从历史对话中学习
class LearningAgent(autogen.ConversableAgent):
    def __init__(self, *args, **kwargs):
        super().__init__(*args, **kwargs)
        self.strategy_history = []
        
    def post_process_reply(self, reply):
        # 记录策略和结果
        outcome = self.evaluate_outcome(reply)
        self.strategy_history.append({
            "context": self.last_context,
            "strategy": reply,
            "outcome": outcome
        })
        # 动态调整策略
        self.adapt_strategy_based_on_history()
        return reply
```

## 调试与优化

### 日志与监控

```python
# 启用详细日志
import logging
logging.basicConfig(level=logging.DEBUG)

# 记录每轮对话
for agent in groupchat.agents:
    agent.register_reply(
        trigger=lambda sender, message, recipient: True,
        reply_func=lambda sender, message, recipient: 
            print(f"[{sender.name} -> {recipient.name}]: {message}") or None
    )
```

### 性能优化技巧

1. **智能体数量**：3-5 个智能体通常效果最佳
2. **轮数限制**：设置合理的 max_round
3. **上下文管理**：定期压缩历史消息
4. **并行执行**：独立子任务可以并行处理

## AutoGen 与其他框架对比

| 特性 | AutoGen | LangChain Agents | CrewAI |
|------|--------|-----------------|--------|
| 多智能体 | ✅ 原生支持 | ⚠️ 需要自行实现 | ✅ 原生支持 |
| 代码执行 | ✅ 内置沙箱 | ⚠️ 需要配置 | ⚠️ 有限支持 |
| 人类交互 | ✅ 灵活模式 | ⚠️ 基础支持 | ✅ 支持 |
| 群聊管理 | ✅ 强大 | ❌ 无 | ✅ 基础 |
| 自定义能力 | ✅ 高度灵活 | ✅ 灵活 | ⚠️ 中等 |
| 学习曲线 | ⚠️ 中等 | ⚠️ 中等 | ✅ 简单 |

## 相关资源

- [AutoGen 官方网站](https://microsoft.github.io/autogen/)
- [GitHub 仓库](https://github.com/microsoft/autogen)
- [官方文档](https://microsoft.github.io/autogen/docs/Getting-Started)
- [示例代码库](https://github.com/microsoft/autogen/tree/main/samples)
- [AutoGen 论文](https://arxiv.org/abs/2308.08155) - AutoGen: Enabling Next-Gen LLM Applications via Multi-Agent Conversation
- [AutoGen Studio](https://github.com/microsoft/autogen/tree/main/samples/apps/autogen-studio) - 可视化界面
- [Discord 社区](https://discord.gg/pAbnFJrkgZ)
