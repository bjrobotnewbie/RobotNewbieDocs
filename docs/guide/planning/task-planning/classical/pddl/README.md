# PDDL (Planning Domain Definition Language)

PDDL 是标准化的规划问题描述语言，用于形式化定义规划领域和问题，是自动规划研究和应用的事实标准。它提供了统一的方式描述动作、状态和目标，使得不同规划器可以使用相同的输入格式。

## 简介

PDDL（Planning Domain Definition Language）是 1998 年为国际规划竞赛（IPC）设计的标准化语言，用于描述 AI 规划问题。它分离了领域知识（动作模型）和具体问题（初始状态、目标），使得规划器可以通用地解决各类规划问题。

## 核心概念

### 语言组成

| 组成部分 | 说明 | 示例 |
|---------|------|------|
| **Domain** | 领域定义，包含类型、谓词、动作 | 机器人搬运领域 |
| **Problem** | 具体问题，包含对象、初始状态、目标 | 具体搬运任务 |

### 类型系统

PDDL 支持简单的类型层次结构：
```
:types
    robot - object
    location - object
    item - object
```

### 谓词 (Predicate)

描述世界状态的布尔表达式：
```
:predicates
    (at ?r - robot ?l - location)    ; 机器人在位置
    (holding ?r - robot ?i - item)   ; 机器人持有物品
    (at ?i - item ?l - location)      ; 物品在位置
```

### 动作 (Action)

定义状态转换规则：

| 组成部分 | 说明 |
|---------|------|
| **参数** | 动作涉及的对象 |
| **前置条件** | 执行动作前必须满足的条件 |
| **效果** | 执行动作后的状态变化 |

## 核心特性

### 标准 PDDL 1.2 / 2.1
- ✅ 类型化对象
- ✅ 一阶逻辑条件和效果
- ✅ 负条件
- ✅ 量化表达式
- ✅ 相等谓词

### 常用扩展
- **PDDL+**：连续时间和数值变化
- **PDDL 3.0**：约束、偏好、轨迹约束
- **PPDDL**：概率规划扩展
- **MA-PDDL**：多智能体规划

### 优势
- ✅ 标准化程度高，跨平台兼容
- ✅ 丰富的规划器生态
- ✅ 形式化语义明确
- ✅ 广泛的研究和应用

### 局限
- ❌ 描述复杂
- ❌ 建模需要专业知识
- ❌ 不适合动态环境
- ❌ 数值支持有限

## 主流规划器

### 经典规划器

#### Fast Downward
- **特点**：最流行的启发式搜索规划器
- **支持**：PDDL 1.2, 2.1, 3.0
- **项目地址**：https://github.com/aibasel/downward
- **文档**：https://www.fast-downward.org/

#### LAMA
- **特点**：基于地标计数的启发式
- **成就**：多次国际规划竞赛冠军
- **集成**：Fast Downward 插件

#### FF
- **特点**：前向搜索，忽略删除列表启发式
- **优势**：速度快，适合经典规划
- **项目地址**：https://fai.cs.uni-saarland.de/hoffmann/ff.html

#### POPF
- **特点**：数值时间规划器
- **支持**：PDDL+ 连续变化
- **项目地址**：https://github.com/popftif/popf-tif

### ROS 集成

#### ROSPlan
- **特点**：ROS 生态规划框架
- **功能**：PDDL 建模、规划、执行、监控
- **项目地址**：https://github.com/KCL-Planning/ROSPlan
- **教程**：https://kcl-planning.github.io/ROSPlan/

## 应用场景

### 服务机器人
- 多步骤任务规划
- 资源调度
- 任务优先级处理

### 工业自动化
- 装配线调度
- 机器人协作规划
- 生产流程优化

### 物流系统
- 仓库货物搬运
- 多机器人路径规划
- 任务分配优化

### 游戏 AI
- NPC 行为规划
- 关卡设计辅助
- 动态剧情生成

## 快速开始

### PDDL 领域定义示例

```
(define (domain robot-delivery)
    (:requirements :strips :typing)
    
    (:types
        robot - object
        location - object
        item - object
    )
    
    (:predicates
        (at ?r - robot ?l - location)
        (at ?i - item ?l - location)
        (holding ?r - robot ?i - item)
        (connected ?from - location ?to - location)
    )
    
    (:action move
        :parameters (?r - robot ?from - location ?to - location)
        :precondition (and
            (at ?r ?from)
            (connected ?from ?to)
        )
        :effect (and
            (at ?r ?to)
            (not (at ?r ?from))
        )
    )
    
    (:action pick
        :parameters (?r - robot ?i - item ?l - location)
        :precondition (and
            (at ?r ?l)
            (at ?i ?l)
        )
        :effect (and
            (holding ?r ?i)
            (not (at ?i ?l))
        )
    )
    
    (:action place
        :parameters (?r - robot ?i - item ?l - location)
        :precondition (and
            (at ?r ?l)
            (holding ?r ?i)
        )
        :effect (and
            (at ?i ?l)
            (not (holding ?r ?i))
        )
    )
)
```

### PDDL 问题定义示例

```
(define (problem delivery-problem-1)
    (:domain robot-delivery)
    
    (:objects
        robot1 - robot
        roomA roomB roomC - location
        package1 package2 - item
    )
    
    (:init
        (at robot1 roomA)
        (at package1 roomA)
        (at package2 roomB)
        (connected roomA roomB)
        (connected roomB roomA)
        (connected roomB roomC)
        (connected roomC roomB)
    )
    
    (:goal (and
        (at package1 roomC)
        (at package2 roomC)
        (at robot1 roomA)
    ))
)
```

### 使用 Fast Downward 规划

```bash
# 命令行调用
./fast-downward.py domain.pddl problem.pddl \
    --search "astar(lmcut())"

# 使用 LAMA 配置
./fast-downward.py domain.pddl problem.pddl \
    --alias lama-first
```

### Python 集成示例

```python
import subprocess
import re

def run_planner(domain_file, problem_file):
    cmd = [
        './fast-downward.py',
        domain_file,
        problem_file,
        '--search', 'astar(lmcut())'
    ]
    
    result = subprocess.run(cmd, capture_output=True, text=True)
    
    # 解析计划
    plan = []
    for line in result.stdout.split('\n'):
        if line.startswith('(') and line.endswith(')'):
            plan.append(line.strip())
    
    return plan

# 执行规划
plan = run_planner('domain.pddl', 'problem.pddl')
print('规划得到的动作序列:')
for action in plan:
    print(f'  {action}')
```

## 设计模式

### 1. 资源管理模式

```
(:predicates
    (available ?resource)
    (using ?agent ?resource)
)

(:action acquire
    :parameters (?a ?r)
    :precondition (available ?r)
    :effect (and (using ?a ?r) (not (available ?r)))
)

(:action release
    :parameters (?a ?r)
    :precondition (using ?a ?r)
    :effect (available ?r)
)
```

### 2. 层次化任务模式

```
;; 高层任务分解为子任务
(:action do-delivery
    :parameters (?r ?i ?from ?to)
    :precondition (and (at ?r ?from) (at ?i ?from))
    :effect ...
)
```

### 3. 条件效果模式

```
(:action move-with-load
    :parameters (?r ?from ?to)
    :precondition (at ?r ?from)
    :effect (and
        (at ?r ?to)
        (not (at ?r ?from))
        (when (holding ?r ?i)
            (and (at ?i ?to) (not (at ?i ?from)))
        )
    )
)
```

## 最佳实践

### 1. 建模建议
- **保持简单**：从最小功能开始，逐步扩展
- **类型设计**：合理的类型层次结构
- **谓词粒度**：避免过细或过粗
- **动作抽象**：动作粒度适中

### 2. 性能优化
- **选择合适的规划器**：根据问题特性选择
- **启发式函数**：使用领域特定启发式
- **领域约束**：利用公理和约束剪枝
- **问题分解**：大问题拆分为小问题

### 3. 调试方法
- **使用 VAL 验证**：PDDL 语法检查工具
- **可视化计划**：图形化展示动作序列
- **增量测试**：先简单后复杂
- **日志分析**：分析规划器输出

## 常用工具

### 编辑工具
- **VS Code PDDL 插件**：语法高亮、验证
- **PDDL Studio**：专业编辑器
- **Web Planner**：在线编辑和规划

### 验证工具
- **VAL**：PDDL 验证器
- **Plan Validator**：计划验证工具

### 可视化工具
- **PlanViz**：计划可视化
- **PDDL Viewer**：领域可视化

## PDDL 版本对比

| 版本 | 年份 | 主要特性 |
|------|-----|---------|
| PDDL 1.2 | 1998 | 基础 STRIPS, 类型 |
| PDDL 2.1 | 2002 | 数值, 时间,  durative actions |
| PDDL+ | 2005 | 连续变化, 过程, 事件 |
| PDDL 3.0 | 2008 | 偏好, 约束, 轨迹 |

## 相关资源

- [PDDL 官方文档](https://planning.wiki/)
- [Fast Downward 文档](https://www.fast-downward.org/)
- [Planning.Wiki 社区](https://planning.wiki/)
- [ROSPlan 教程](https://kcl-planning.github.io/ROSPlan/)
- [ICAPS 会议](https://www.icaps-conference.org/)
- [Automated Planning 教材](https://www.morganclaypool.com/doi/10.2200/S00232ED1V01Y200907AIM005)
