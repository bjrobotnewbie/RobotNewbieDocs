# 传统任务规划

传统任务规划基于形式化逻辑和符号推理，经过数十年的发展，理论基础扎实，在工业界有广泛应用。这类方法的特点是可解释性强、确定性高，但需要人工建模，泛化能力有限。

## 分类总览

| 方法 | 核心思想 | 优势 | 局限 | 典型应用 |
|------|---------|------|------|---------|
| **行为树** | 树形结构的任务执行流 | 可视化好、模块化强 | 复杂任务难以维护 | 游戏AI、服务机器人 |
| **HTN** | 层次化任务分解 | 搜索效率高、领域知识利用好 | 分解方法需要人工设计 | 服务机器人、工业自动化 |
| **PDDL** | 标准化规划语言 | 通用、规划器丰富 | 建模复杂、学习曲线陡 | 物流调度、多机器人协调 |

---

## 方法详解

### 1. [行为树 (Behavior Tree)](/guide/planning/task-planning/classical/behavior-tree/README)

行为树是一种树形结构的任务执行建模方法，起源于游戏 AI 领域，现在广泛应用于机器人系统。

**核心概念：**
- **控制节点**：Sequence（顺序执行）、Selector（选择执行）、Parallel（并行执行）
- **装饰节点**：Inverter（取反）、Repeat（重复）、Retry（重试）
- **行为节点**：Condition（条件检查）、Action（执行动作）

**典型架构：**
```
根节点
└─ Selector
   ├─ Sequence: 取物任务
   │  ├─ Condition: 看到目标
   │  ├─ Action: 移动到目标
   │  └─ Action: 抓取
   └─ Sequence: 搜索任务
      ├─ Action: 环顾四周
      └─ Action: 移动到下一点
```

**主要框架：**
- BehaviorTree.CPP - C++ 高性能实现，ROS 2 集成
- py_trees - Python 实现，适合快速原型开发
- Unreal Engine / Unity - 游戏引擎内置支持

---

### 2. [层次任务网络 (HTN)](/guide/planning/task-planning/classical/htn/README)

层次任务网络通过递归地将复合任务分解为更简单的子任务，直到达到可执行的原语动作。

**核心概念：**
- **任务**：原语任务（可执行）、复合任务（需分解）
- **方法**：定义如何分解复合任务
- **操作符**：定义原语任务的前置条件和效果

**分解示例：**
```
任务：取物送目标
  └─ 方法：标准取送流程
     ├─ 子任务1：移动到取物点
     ├─ 子任务2：抓取物体
     ├─ 子任务3：移动到放置点
     └─ 子任务4：放置物体
```

**主要实现：**
- SHOP2 - 经典 HTN 规划器
- PyHop - Python 简单实现
- PANDA - 现代 HTN 规划器，支持部分有序规划

---

### 3. [规划域定义语言 (PDDL)](/guide/planning/task-planning/classical/pddl/README)

PDDL 是人工智能规划领域的标准化语言，用于描述规划问题的领域知识和具体问题。

**核心组成：**
- **Domain 文件**：定义谓词、动作、类型
- **Problem 文件**：定义对象、初始状态、目标

**PDDL 示例结构：**
```lisp
(define (domain robot-delivery)
  (:types robot location item - object)
  (:predicates
    (at ?r - robot ?l - location)
    (holding ?r - robot ?i - item)
    (connected ?from ?to - location))
  (:action move
    :parameters (?r - robot ?from ?to - location)
    :precondition (and (at ?r ?from) (connected ?from ?to))
    :effect (and (at ?r ?to) (not (at ?r ?from)))))
```

**主要规划器：**
- Fast Downward - 最流行的启发式搜索规划器
- LAMA - 地标计数启发式规划器
- FF - 前向搜索规划器
- POPF - 数值时间规划器

---

## 技术选型对比

| 维度 | 行为树 | HTN | PDDL |
|------|--------|-----|------|
| **建模难度** | 低，直观 | 中，层次化思考 | 高，形式化逻辑 |
| **可解释性** | 高，可视化好 | 中，层次结构 | 中，需要专业知识 |
| **泛化能力** | 低，硬编码 | 中，方法可复用 | 高，领域通用 |
| **实时性** | 高，执行效率 | 中，分解开销 | 低，规划时间长 |
| **工具支持** | 好，可视化编辑 | 一般 | 好，多规划器 |
| **学习曲线** | 平缓 | 中等 | 陡峭 |

---

## 混合使用场景

在复杂机器人系统中，通常会组合使用多种规划方法：

### 典型组合方案 1：
```
高层任务分解：HTN 或 PDDL
  ↓ 生成可执行子任务
执行流控制：行为树
  ↓ 调用机器人能力
底层运动控制：运动规划 + 控制
```

### 典型组合方案 2：
```
任务目标：PDDL 规划器生成动作序列
  ↓
执行编排：行为树控制执行流
  ↓
异常处理：行为树的回退和恢复机制
```

---

## 相关资源

### 行为树
- [BehaviorTree.CPP 文档](https://www.behaviortree.dev/)
- [py_trees 文档](https://py-trees.readthedocs.io/)
- [Behavior Trees for Robotics 教程](https://arxiv.org/abs/1709.00084)

### HTN
- [SHOP2 官方网站](http://www.cs.umd.edu/projects/shop/)
- [PyHop 代码库](https://bitbucket.org/dananau/pyhop/)
- [HTN Planning Survey](https://arxiv.org/abs/1905.05714)

### PDDL
- [Planning.Wiki](https://planning.wiki/)
- [Fast Downward 文档](https://www.fast-downward.org/)
- [PDDL 教程](https://github.com/pucrs-automated-planning/pddl-course)
