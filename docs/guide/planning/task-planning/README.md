# 任务规划 (Task Planning)

任务规划是机器人智能决策的核心技术，研究如何将复杂的高层目标分解为可执行的子任务序列。根据技术范式的不同，任务规划主要分为两大方向：**传统符号规划**和**大语言模型驱动的规划**。

## 分类总览

| 分类 | 核心思想 | 典型方法 | 优势 | 局限性 |
|------|---------|---------|------|--------|
| **传统任务规划** | 基于规则和符号逻辑 | 行为树、HTN、PDDL | 可解释性强、确定性高 | 泛化能力弱、需要人工建模 |
| **LLM 驱动规划** | 基于语义理解和常识推理 | ReAct、Reflexion、AutoGen | 泛化能力强、零样本适配 | 可解释性弱、存在幻觉 |

---

## 一、传统任务规划

基于形式化逻辑和符号推理的规划方法，经过数十年的发展，理论基础扎实，在工业界有广泛应用。

### 主要方法

#### 1. [行为树 (Behavior Tree)](/guide/planning/task-planning/classical/behavior-tree/README)

行为树是一种层级化的任务执行建模方法，通过组合基本行为节点实现复杂任务逻辑。广泛应用于游戏 AI 和机器人系统。

**核心特性：**
- 可视化程度高，易于理解和调试
- 模块化设计，节点可复用
- 支持条件判断、顺序执行、并行执行等
- 成熟的生态系统和工具链

**典型应用：**
- 游戏 NPC 行为建模
- 服务机器人任务编排
- 工业机器人流程控制

#### 2. [层次任务网络 (HTN)](/guide/planning/task-planning/classical/htn/README)

层次任务网络通过递归地将复合任务分解为更简单的子任务，直到达到可执行的原语动作。

**核心特性：**
- 利用领域知识指导搜索，效率高
- 自然的层次化表示
- 支持多种分解策略
- 可解释性强

**典型应用：**
- 服务机器人家庭任务
- 工业自动化流程
- 航天任务规划

#### 3. [规划域定义语言 (PDDL)](/guide/planning/task-planning/classical/pddl/README)

PDDL 是标准化的规划问题描述语言，分离了领域知识和具体问题，使得不同规划器可以通用地解决各类规划问题。

**核心特性：**
- 标准化程度高，跨平台兼容
- 丰富的规划器生态系统
- 形式化语义明确
- 支持扩展（数值、时间、概率）

**典型应用：**
- 物流系统调度
- 多机器人任务分配
- 自动化生产流程

---

## 二、LLM 驱动的任务规划

利用大语言模型的语义理解能力、常识知识和推理能力，直接从自然语言指令生成任务计划。这是当前最活跃的研究方向之一。

### 主要范式

#### 1. [ReAct (Reasoning + Acting)](/guide/planning/task-planning/llm-driven/react/README)

ReAct 将推理和行动结合，通过"思考-行动-观察"的循环迭代来解决复杂任务。

**核心流程：**
```
思考 (Thought) → 行动 (Action) → 观察 (Observation) → ... → 答案
```

**核心特性：**
- 可解释性强，能看到完整推理链
- 支持工具调用和环境交互
- 可以处理复杂多步骤任务
- 易于调试和提示工程优化

**典型应用：**
- 多跳知识问答
- 代码编写与调试
- 数据分析
- 机器人高层任务规划

#### 2. [Reflexion (反思式规划)](/guide/planning/task-planning/llm-driven/reflexion/README)

Reflexion 在 ReAct 的基础上增加了反思机制，通过自我评估和错误修正来提升任务成功率。

**核心流程：**
```
尝试 → 执行 → 评估 → 反思 → 下一次尝试
```

**核心特性：**
- 从失败中学习，迭代改进
- 显著提升复杂任务成功率
- 自我纠错能力强
- 可解释性好，能看到改进过程

**典型应用：**
- 代码编写与调试
- 数学推理题求解
- Bug 修复
- 复杂创意写作

#### 3. [AutoGen (多智能体协作)](/guide/planning/task-planning/llm-driven/autogen/README)

AutoGen 是微软开发的多智能体框架，通过多个专业化智能体的分工协作来完成复杂任务。

**核心架构：**
```
用户需求
  ↓
规划者 Agent → 任务分解
  ↓
执行者 Agent → 分步执行
  ↓
批评者 Agent → 评估反馈
  ↓
反思者 Agent → 策略调整
```

**核心特性：**
- 多智能体协作，分工明确
- 内置代码执行沙箱
- 支持人类在回路中
- 灵活的对话模式
- 丰富的自定义能力

**典型应用：**
- 软件开发团队协作
- 复杂研究任务
- 多步骤工程问题
- 机器人任务规划与执行

---

## 三、与其他规划层级的关系

### 规划层级体系

| 层级 | 抽象程度 | 输入 | 输出 | 典型技术 |
|------|---------|------|------|---------|
| **任务规划** | 最高 | 自然语言目标 | 子任务序列 | 行为树、HTN、LLM Agent |
| **运动规划** | 中间 | 目标位姿 | 关节/末端轨迹 | MoveIt、CHOMP、OMPL |
| **路径规划** | 最低 | 起点终点 | 几何路径点 | A*、RRT、Dijkstra |

### 层级协作示例

```
用户指令："把桌子上的杯子拿到厨房"
  ↓ 任务规划层（LLM Agent）
子任务1：移动到桌子位置
子任务2：抓取杯子
子任务3：移动到厨房
子任务4：放置杯子
  ↓ 运动规划层（MoveIt）
关节角度序列 + 速度约束
  ↓ 路径规划层（A* + DWA）
路径点序列 + 避障
  ↓ 执行控制
机器人实际运动
```

---

## 四、技术选型指南

### 选择传统规划如果：
- ✅ 环境和任务高度结构化
- ✅ 需要严格的确定性和可预测性
- ✅ 有明确的领域知识和规则
- ✅ 安全性要求极高
- ✅ 任务类型相对固定

### 选择 LLM 驱动规划如果：
- ✅ 任务开放式，难以预定义所有情况
- ✅ 需要处理自然语言指令
- ✅ 环境动态变化频繁
- ✅ 需要一定的泛化能力
- ✅ 可以接受一定的不确定性

### 混合架构推荐：

```
高层决策：LLM Agent (ReAct / Reflexion / AutoGen)
  ↓ 生成可执行子任务
中层编排：行为树 / HTN
  ↓ 调用底层能力
底层执行：运动规划 + 控制
```

---

## 五、发展趋势

### 1. 神经符号结合
结合神经网络的泛化能力和符号方法的可解释性，是当前重要的研究方向。

### 2. 多模态规划
整合视觉、语言、触觉等多种感知模态，提升规划的鲁棒性和适应性。

### 3. 终身学习规划
让机器人在执行过程中不断学习和改进规划策略，积累经验。

### 4. 多智能体协同
多个机器人或智能体之间的任务分配和协作规划，在仓储、物流等领域有广阔应用。

---

## 详细文档导航

### 传统任务规划
- [行为树 (Behavior Tree)](/guide/planning/task-planning/classical/behavior-tree/README)
- [层次任务网络 (HTN)](/guide/planning/task-planning/classical/htn/README)
- [规划域定义语言 (PDDL)](/guide/planning/task-planning/classical/pddl/README)

### LLM 驱动的规划
- [ReAct (推理+行动)](/guide/planning/task-planning/llm-driven/react/README)
- [Reflexion (反思式规划)](/guide/planning/task-planning/llm-driven/reflexion/README)
- [AutoGen (多智能体协作)](/guide/planning/task-planning/llm-driven/autogen/README)

### 任务规划库与框架

- [BehaviorTree.CPP](/guide/planning/BehaviorTree.CPP/README) - C++ 行为树框架，用于机器人任务编排与行为决策
- [bonsai](/guide/planning/bonsai/README) - Rust 实现的行为树库，支持 Python 绑定
- [ros2_planning_system](/guide/planning/ros2_planning_system/README) - ROS2 基于 PDDL 的自动规划系统
- [mctx](/guide/planning/mctx/README) - DeepMind JAX 蒙特卡洛树搜索（MCTS）库，含 AlphaZero、MuZero
- [open_spiel](/guide/planning/open_spiel/README) - DeepMind 博弈强化学习研究框架，含搜索规划算法
