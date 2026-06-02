# Reflexion (反思式规划)

Reflexion 是一种基于反思机制的 LLM 智能体架构，通过让模型自我评估、反思错误并调整策略，显著提升复杂任务的解决能力和鲁棒性。它在 ReAct 的基础上增加了反思环节，使智能体能够从失败中学习并改进。

## 简介

Reflexion 是由 Noah Shinn 等人在 2023 年提出的方法，核心思想是模仿人类的反思学习过程。当智能体完成一次任务尝试后，会对自己的表现进行批判性反思，总结经验教训，并在下一次尝试中应用这些经验改进策略。

## 核心概念

### 基本流程

```
尝试 (Trial) → 执行 (Act) → 评估 (Evaluate) → 反思 (Reflect) → 下一次尝试
```

### 核心组件

| 组件 | 说明 | 典型实现 |
|------|------|---------|
| **Actor** | 执行任务的智能体，通常基于 ReAct | ReAct Agent |
| **Evaluator** | 评估表现，判断成功或失败 | 评分函数、成功检测 |
| **Reflector** | 生成反思，总结经验教训 | LLM 生成改进建议 |
| **Memory** | 存储历史反思和经验 | 短期记忆、长期记忆 |

## 核心特性

### 优势
- ✅ 从失败中学习，迭代改进
- ✅ 显著提升复杂任务成功率
- ✅ 自我纠错能力强
- ✅ 可解释性好，能看到改进过程
- ✅ 适用于各类任务类型

### 局限
- ❌ 需要多次尝试，耗时较长
- ❌ 反思质量依赖 LLM 能力
- ❌ 可能陷入局部最优
- ❌ 评估标准设计困难
- ❌ 记忆管理复杂度高

## 典型实现框架

### 官方 Reflexion
- **特点**：原始论文实现，支持多轮反思
- **项目地址**：https://github.com/noahshinn/reflexion
- **论文**：Reflexion: Language Agents with Verbal Reinforcement Learning

### LangGraph
- **特点**：基于状态机的图编排，支持循环
- **项目地址**：https://github.com/langchain-ai/langgraph
- **文档**：https://langchain-ai.github.io/langgraph/
- **功能**：支持反思循环、多智能体、状态管理

### AutoGen (Reflective Agents)
- **特点**：微软多智能体框架，内置反思模式
- **项目地址**：https://github.com/microsoft/autogen
- **文档**：https://microsoft.github.io/autogen/
- **功能**：多智能体对话、反思、代码执行

### OpenDevin
- **特点**：AI 软件开发智能体，采用反思机制
- **项目地址**：https://github.com/OpenDevin/OpenDevin
- **功能**：代码编写、调试、测试、反思改进

## 应用场景

### 软件开发
- 代码编写与调试
- Bug 修复
- 测试生成
- 代码审查与优化

### 数学推理
- 复杂数学题求解
- 证明验证与改进
- 多步骤推理任务

### 问答系统
- 多跳知识问答
- 事实核查
- 复杂信息整合

### 机器人任务
- 高层任务规划
- 失败恢复策略
- 动态环境适应

### 创意写作
- 内容生成与迭代
- 风格优化
- 多轮润色

## 快速开始

### 基础 Reflexion 实现

```python
import openai
from typing import List, Dict

class ReflexionAgent:
    def __init__(self, max_trials: int = 3):
        self.max_trials = max_trials
        self.memory: List[Dict] = []
        
    def run_trial(self, task: str, reflection: str = "") -> str:
        """执行一次任务尝试"""
        messages = [
            {"role": "system", "content": """
你是一个智能助手。仔细思考问题，逐步解决。

如果有之前的反思，请参考并改进：
"""},
            {"role": "user", "content": f"""
任务: {task}

之前的反思: {reflection if reflection else "无"}

请解决这个任务。
"""}
        ]
        
        response = openai.ChatCompletion.create(
            model="gpt-4",
            messages=messages
        )
        
        return response.choices[0].message.content
    
    def evaluate(self, result: str, task: str) -> tuple[bool, str]:
        """评估结果，返回是否成功和反馈"""
        evaluation = openai.ChatCompletion.create(
            model="gpt-4",
            messages=[
                {"role": "system", "content": """
评估任务完成质量。返回格式：
成功: [是/否]
评分: [1-10]
反馈: [具体评价]
"""},
                {"role": "user", "content": f"""
任务: {task}
结果: {result}
"""}
            ]
        )
        
        eval_text = evaluation.choices[0].message.content
        is_success = "是" in eval_text.split("成功:")[1].split("\n")[0]
        
        return is_success, eval_text
    
    def reflect(self, task: str, result: str, evaluation: str) -> str:
        """生成反思"""
        reflection = openai.ChatCompletion.create(
            model="gpt-4",
            messages=[
                {"role": "system", "content": """
作为批判性反思者，请分析这次尝试的问题所在，并给出具体的改进建议。

格式：
问题分析: [主要问题]
改进建议: [具体建议]
经验总结: [可以应用的经验]
"""},
                {"role": "user", "content": f"""
任务: {task}
尝试结果: {result}
评估: {evaluation}

请进行反思：
"""}
            ]
        )
        
        return reflection.choices[0].message.content
    
    def solve(self, task: str) -> str:
        """主循环：尝试-评估-反思"""
        reflection = ""
        
        for trial in range(self.max_trials):
            print(f"\n=== 第 {trial + 1} 次尝试 ===")
            
            # 执行尝试
            result = self.run_trial(task, reflection)
            print(f"结果:\n{result}")
            
            # 评估
            is_success, evaluation = self.evaluate(result, task)
            print(f"\n评估:\n{evaluation}")
            
            if is_success:
                print("\n✓ 任务成功！")
                return result
            
            # 反思
            print("\n正在反思...")
            reflection = self.reflect(task, result, evaluation)
            print(f"反思:\n{reflection}")
            
            # 保存到记忆
            self.memory.append({
                "trial": trial + 1,
                "result": result,
                "evaluation": evaluation,
                "reflection": reflection
            })
        
        print(f"\n✗ 达到最大尝试次数")
        return result
```

### 使用示例

```python
# 创建智能体
agent = ReflexionAgent(max_trials=3)

# 解决任务
result = agent.solve("""
编写一个 Python 函数，实现快速排序算法。
要求：
1. 正确实现快速排序
2. 包含详细注释
3. 包含测试用例
""")

print("\n最终结果:")
print(result)
```

### LangGraph 实现反思循环

```python
from langgraph.graph import StateGraph, END
from typing import TypedDict, Annotated
import operator

class AgentState(TypedDict):
    task: str
    current_result: str
    reflection: str
    trial_count: int
    success: bool

def act(state: AgentState) -> AgentState:
    """执行动作"""
    result = execute_task(state["task"], state["reflection"])
    return {"current_result": result, "trial_count": state["trial_count"] + 1}

def evaluate(state: AgentState) -> AgentState:
    """评估结果"""
    success, feedback = evaluate_result(state["task"], state["current_result"])
    return {"success": success}

def reflect(state: AgentState) -> AgentState:
    """生成反思"""
    reflection = generate_reflection(state["task"], state["current_result"])
    return {"reflection": reflection}

def should_continue(state: AgentState) -> str:
    """判断是否继续"""
    if state["success"]:
        return "end"
    if state["trial_count"] >= 3:
        return "end"
    return "reflect"

# 构建图
workflow = StateGraph(AgentState)

# 添加节点
workflow.add_node("act", act)
workflow.add_node("evaluate", evaluate)
workflow.add_node("reflect", reflect)

# 设置边
workflow.set_entry_point("act")
workflow.add_edge("act", "evaluate")
workflow.add_conditional_edges(
    "evaluate",
    should_continue,
    {
        "reflect": "reflect",
        "end": END
    }
)
workflow.add_edge("reflect", "act")

# 编译运行
app = workflow.compile()
result = app.invoke({
    "task": "编写快速排序代码",
    "reflection": "",
    "trial_count": 0,
    "success": False
})
```

## 设计模式

### 1. 多层反思模式

```python
class MultiLevelReflector:
    def reflect_inference_trace(self):
        """反思推理轨迹的逻辑错误"""
        pass
    
    def reflect_heuristic(self):
        """反思策略和方法选择"""
        pass
        
    def reflect_strategy(self):
        """反思整体策略"""
        pass
```

### 2. 经验记忆模式

```python
class ExperienceMemory:
    def __init__(self):
        self.success_experiences = []
        self.failure_experiences = []
    
    def add_experience(self, task, result, reflection):
        """添加经验"""
        pass
        
    def retrieve_relevant(self, current_task):
        """检索相关经验"""
        pass
```

### 3. 滚动窗口反思

```python
class RollingReflector:
    def __init__(self, window_size: int = 5):
        self.window_size = window_size
        self.recent_attempts = []
    
    def generate_reflection(self):
        """基于最近 N 次尝试生成反思"""
        # 分析模式和常见错误
        # 生成综合改进建议
        pass
```

## 最佳实践

### 1. 评估设计
- **明确的成功标准**：避免模糊的评估
- **量化指标**：使用可量化的评分
- **多维度评估**：正确性、效率、可读性等
- **人工复核**：关键任务加入人类评估

### 2. 反思提示工程
- **引导批判性思考**：避免泛泛而谈
- **要求具体建议**：可操作的改进建议
- **结构化输出**：固定格式便于解析
- **正反示例**：提供好的和坏的反思示例

### 3. 记忆管理
- **去冗余**：避免存储重复经验
- **优先级**：重要经验优先存储
- **检索机制**：基于相似度检索相关经验
- **遗忘策略**：定期清理过时经验

### 4. 性能优化
- **并行尝试**：多个独立尝试并行
- **早期终止**：明显失败的尝试提前终止
- **缓存机制**：相同子任务结果缓存
- **渐进式改进**：每次只改进一个方面

## 高级扩展

### 1. 多智能体协作反思

```
主智能体 → 执行任务
评估智能体 → 独立评估
批评智能体 → 深度反思
协作改进
```

### 2. 强化学习结合

将反思转化为奖励信号，结合强化学习：
- 成功 → 正奖励
- 失败但有进步 → 中等奖励
- 有效反思 → 额外奖励

### 3. 课程学习

从简单任务开始，逐步增加难度：
1. 简单任务建立基础能力
2. 中等任务积累反思经验
3. 复杂任务应用综合能力

## Reflexion 变种对比

| 方法 | 反思时机 | 反思深度 | 适用场景 |
|------|---------|---------|---------|
| **单轮反思** | 失败后反思 | 浅 | 简单任务 |
| **多轮迭代反思** | 每轮后反思 | 中 | 中等任务 |
| **深度反思** | 分层多维度 | 深 | 复杂任务 |
| **分布式反思** | 多智能体各自反思 | 很深 | 超复杂任务 |

## 相关资源

- [Reflexion 论文](https://arxiv.org/abs/2303.11366) - Reflexion: Language Agents with Verbal Reinforcement Learning
- [官方 GitHub 仓库](https://github.com/noahshinn/reflexion) - Reflexion 实现
- [LangGraph 文档](https://langchain-ai.github.io/langgraph/) - 图编排框架
- [AutoGen](https://github.com/microsoft/autogen) - 多智能体框架
- [OpenDevin](https://github.com/OpenDevin/OpenDevin) - AI 开发智能体
- [Self-Refine 论文](https://arxiv.org/abs/2303.17651) - 自我改进相关工作
