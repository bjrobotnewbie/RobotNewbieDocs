# 层次任务网络 (Hierarchical Task Network, HTN)

层次任务网络是一种基于任务分解的规划方法，通过递归地将复杂任务分解为更简单的子任务，直到达到可执行的原语动作，是经典 AI 规划的重要方法之一。

## 简介

HTN（Hierarchical Task Network）规划通过任务分解网络描述规划问题，使用方法（Method）将复合任务分解为子任务网络，最终生成可执行的动作序列。与状态空间规划不同，HTN 利用领域知识指导搜索，效率通常更高。

## 核心概念

### 任务类型

| 任务类型 | 说明 | 示例 |
|---------|------|------|
| **原语任务 (Primitive Task)** | 可直接执行的原子动作 | 移动、抓取、放置 |
| **复合任务 (Compound Task)** | 需要分解的高层任务 | 取物、运送、装配 |
| **目标任务 (Goal Task)** | 达到特定状态的任务 | 物体在目标位置 |

### 方法 (Method)

方法定义如何将复合任务分解为子任务网络，包含：
- **前置条件**：可应用该方法的条件
- **子任务网络**：分解后的子任务及顺序关系
- **约束条件**：变量绑定、时间约束等

### 操作符 (Operator)

操作符定义原语任务的执行效果：
- **前置条件**：执行前必须满足
- **效果**：执行后的状态变化
- **代价**：执行该动作的成本

## 核心特性

### 优势
- ✅ 利用领域知识，搜索效率高
- ✅ 自然的层次化表示
- ✅ 支持领域特定的启发式
- ✅ 适合结构化任务
- ✅ 可解释性强

### 局限
- ❌ 需要人工设计分解方法
- ❌ 方法设计需要领域专家
- ❌ 不适合开放式任务
- ❌ 方法设计质量影响规划效果

## 主流实现框架

### SHOP2 / JSHOP2
- **特点**：最经典的 HTN 规划器
- **语言**：Lisp / Java
- **项目地址**：https://github.com/shop-planner/shop2
- **论文**：SHOP2: An HTN Planning System

### PyHop
- **特点**：Python 实现，简单易用
- **项目地址**：https://bitbucket.org/dananau/pyhop
- **文档**：https://bitbucket.org/dananau/pyhop

### ROSPlan
- **特点**：ROS 集成规划框架，支持 HTN
- **项目地址**：https://github.com/KCL-Planning/ROSPlan
- **文档**：https://kcl-planning.github.io/ROSPlan/

## 应用场景

### 服务机器人
- 家庭任务规划（取物、送物、清洁）
- 多步骤任务编排
- 人机协作任务

### 工业自动化
- 装配线任务调度
- 工艺流程规划
- 资源分配优化

### 游戏 AI
- NPC 行为规划
- 任务系统设计
- 剧情推进逻辑

### 航天系统
- 卫星操作规划
- 探测任务调度
- 资源管理

## 快速开始

### PyHop 示例

```python
import pyhop

# 定义状态
state1 = pyhop.State('state1')
state1.loc = {'me': 'office', 'package': 'office'}
state1.have = {'me': []}

# 定义原语操作符
def move(state, agent, loc_from, loc_to):
    if state.loc[agent] == loc_from:
        state.loc[agent] = loc_to
        return state
    return False

def pickup(state, agent, obj):
    if state.loc[agent] == state.loc[obj]:
        state.have[agent].append(obj)
        return state
    return False

def putdown(state, agent, obj):
    if obj in state.have[agent]:
        state.have[agent].remove(obj)
        state.loc[obj] = state.loc[agent]
        return state
    return False

pyhop.declare_operators(move, pickup, putdown)

# 定义分解方法
def transport_by_me(state, obj, destination):
    return [
        ('pickup', 'me', obj),
        ('move', 'me', state.loc[obj], destination),
        ('putdown', 'me', obj)
    ]

pyhop.declare_methods('transport', transport_by_me)

# 执行规划
print("规划结果:")
result = pyhop.pyhop(state1, [('transport', 'package', 'warehouse')], verbose=3)
```

### SHOP2 示例语法

```lisp
;; 定义领域
(defdomain delivery
  (:operators
    (!move ?r ?from ?to
      :precondition (at ?r ?from)
      :effect (and (at ?r ?to) (not (at ?r ?from))))
    
    (!pickup ?r ?pkg
      :precondition (and (at ?r ?loc) (at ?pkg ?loc))
      :effect (and (holding ?r ?pkg) (not (at ?pkg ?loc))))
  )
  
  (:methods
    (deliver ?r ?pkg ?dest)
    ()
    ((!pickup ?r ?pkg)
     (!move ?r ?from ?dest)
     (!putdown ?r ?pkg))
  )
)

;; 定义问题
(defproblem delivery-problem delivery
  (:init (at robot1 room1) (at packageA room1))
  (:goal (at packageA room2))
)
```

## 设计模式

### 1. 任务分解模式

```
复合任务: 完成送餐
├── 方法1: 正常流程
│   ├── 取餐
│   ├── 导航到目标
│   └── 交付
└── 方法2: 故障处理
    ├── 重新规划路径
    ├── 通知用户
    └── 备用配送
```

### 2. 递归分解模式

```
任务: 建造房屋
├── 准备阶段
│   ├── 选址
│   └── 采购材料
├── 施工阶段
│   ├── 打地基
│   ├── 搭建框架
│   └── 内部装修
└── 验收阶段
    ├── 安全检查
    └── 交付使用
```

### 3. 条件分支模式

```
任务: 处理包裹
├── 如果包裹沉重
│   └── 使用叉车
├── 如果包裹易碎
│   └── 小心搬运
└── 否则
    └── 正常搬运
```

## 最佳实践

1. **方法设计**：
   - 方法粒度适中，避免过细或过粗
   - 每个方法应有明确的前置条件
   - 提供多种分解方式增加灵活性

2. **状态表示**：
   - 保持状态表示简洁
   - 使用类型系统约束变量
   - 合理使用公理推导

3. **性能优化**：
   - 设计有效的启发式函数
   - 使用任务分解剪枝搜索空间
   - 考虑增量规划技术

4. **调试方法**：
   - 记录分解过程日志
   - 可视化任务分解树
   - 单元测试每个方法

## HTN vs 其他规划方法

| 特性 | HTN | PDDL | 行为树 |
|------|-----|------|--------|
| 知识表示 | 任务分解 | 动作效果 | 控制流 |
| 搜索方式 | 任务空间 | 状态空间 | 树遍历 |
| 领域知识 | 需设计方法 | 需定义动作 | 需设计节点 |
| 规划效率 | 通常更高 | 取决于领域 | 高 |
| 可解释性 | 高 | 中 | 很高 |
| 适合任务 | 结构化任务 | 通用规划 | 执行控制 |

## 相关资源

- [SHOP2 官方网站](http://www.cs.umd.edu/projects/shop/)
- [PyHop 教程](https://bitbucket.org/dananau/pyhop)
- [Automated Planning 教材](https://www.morganclaypool.com/doi/10.2200/S00232ED1V01Y200907AIM005)
- [ROSPlan 文档](https://kcl-planning.github.io/ROSPlan/)
- [HTN Planning Survey](https://arxiv.org/abs/1905.05714)
