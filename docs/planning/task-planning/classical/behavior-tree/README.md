# 行为树 (Behavior Tree)

行为树是一种层级化的任务执行建模方法，广泛应用于游戏 AI 和机器人系统中，通过组合基本行为节点实现复杂的任务逻辑。

## 简介

行为树（Behavior Tree, BT）是一种用树形结构表示任务执行逻辑的方法，根节点开始遍历，根据节点类型决定执行顺序和条件判断，具有模块化、可复用、可视化好等优点。

## 核心概念

### 控制流节点

| 节点类型 | 功能说明 | 典型应用 |
|---------|---------|---------|
| **Sequence** | 顺序执行所有子节点，全部成功则成功 | 任务流程编排 |
| **Selector** | 选择执行子节点，一个成功则成功 | 故障切换、备选方案 |
| **Parallel** | 并行执行所有子节点 | 多任务并发 |
| **Decorator** | 装饰器，修改子节点行为 | 重复执行、取反 |

### 行为节点

| 节点类型 | 功能说明 | 典型应用 |
|---------|---------|---------|
| **Action** | 执行具体动作 | 移动、抓取、检测 |
| **Condition** | 检查条件是否满足 | 状态判断、环境感知 |

### 返回状态

- **SUCCESS** - 节点执行成功
- **FAILURE** - 节点执行失败
- **RUNNING** - 节点正在执行中

## 核心特性

### 优势
- ✅ 可视化程度高，易于理解和调试
- ✅ 模块化设计，行为节点可复用
- ✅ 支持复杂的任务逻辑组合
- ✅ 非侵入式，与现有系统集成容易
- ✅ 丰富的工具链和生态系统

### 局限
- ❌ 大型行为树可能难以维护
- ❌ 不擅长处理动态规划
- ❌ 学习曲线较陡

## 主流实现框架

### ROS 2 - BehaviorTree.CPP
- **特点**：高性能 C++ 实现，ROS 2 集成
- **项目地址**：https://github.com/BehaviorTree/BehaviorTree.CPP
- **文档**：https://www.behaviortree.dev/
- **ROS 集成**：https://github.com/BehaviorTree/BehaviorTree.ROS2

### py_trees
- **特点**：Python 实现，适合快速原型开发
- **项目地址**：https://github.com/splintered-reality/py_trees
- **文档**：https://py-trees.readthedocs.io/

### Unreal Engine / Unity
- 游戏开发领域广泛应用
- 可视化编辑器支持
- 丰富的社区资源

## 应用场景

### 服务机器人
- 任务流程编排
- 故障恢复逻辑
- 多模态交互

### 工业机器人
- 装配任务流程
- 状态机管理
- 异常处理

### 游戏 AI
- NPC 行为建模
- 决策逻辑
- 状态转换

## 快速开始

### BehaviorTree.CPP 示例

```cpp
#include <behaviortree_cpp/bt_factory.h>
using namespace BT;

// 定义动作节点
NodeStatus ApproachObject() {
    std::cout << "接近目标物体" << std::endl;
    return NodeStatus::SUCCESS;
}

NodeStatus GraspObject() {
    std::cout << "抓取物体" << std::endl;
    return NodeStatus::SUCCESS;
}

int main() {
    BehaviorTreeFactory factory;
    
    // 注册节点
    factory.registerSimpleCondition("是否看到物体", 
        [] { return NodeStatus::SUCCESS; });
    factory.registerSimpleAction("接近物体", ApproachObject);
    factory.registerSimpleAction("抓取物体", GraspObject);
    
    // 创建树
    auto tree = factory.createTreeFromText(R"(
        <root BTCPP_format="4">
            <BehaviorTree ID="MainTree">
                <Sequence>
                    <Condition ID="是否看到物体"/>
                    <Action ID="接近物体"/>
                    <Action ID="抓取物体"/>
                </Sequence>
            </BehaviorTree>
        </root>
    )");
    
    // 执行树
    tree.tickWhileRunning();
    return 0;
}
```

### py_trees 示例

```python
import py_trees

class Approach(py_trees.behaviour.Behaviour):
    def update(self):
        print("接近目标")
        return py_trees.common.Status.SUCCESS

class Grasp(py_trees.behaviour.Behaviour):
    def update(self):
        print("抓取物体")
        return py_trees.common.Status.SUCCESS

# 构建行为树
root = py_trees.composites.Sequence(name="抓取任务")
root.add_child(Approach(name="接近"))
root.add_child(Grasp(name="抓取"))

# 执行
root.tick_once()
```

## 设计模式

### 1. 故障恢复模式

```
Selector
├── 正常执行序列
│   ├── 动作A
│   ├── 动作B
│   └── 动作C
└── 恢复序列
    ├── 诊断问题
    └── 恢复动作
```

### 2. 超时重试模式

```
RetryUntilSuccessful (max_attempts=3)
└── 动作节点
```

### 3. 并行执行模式

```
Parallel (success_threshold=2)
├── 感知任务
├── 规划任务
└── 执行任务
```

## 最佳实践

1. **保持简洁**：避免过深的嵌套，拆分子树
2. **命名规范**：使用清晰的节点命名
3. **错误处理**：每个子任务都应有失败处理
4. **日志记录**：记录节点状态变化便于调试
5. **测试驱动**：对每个行为节点进行单元测试

## 相关资源

- [BehaviorTree.CPP 官方文档](https://www.behaviortree.dev/)
- [py_trees 文档](https://py-trees.readthedocs.io/)
- [Behavior Trees for Robotics 教程](https://arxiv.org/abs/1709.00084)
