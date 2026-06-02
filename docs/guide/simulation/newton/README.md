# Newton - NVIDIA 开源物理引擎

Newton 是由 NVIDIA、Google DeepMind 和 Disney Research 共同开发的开源、可扩展的物理引擎，旨在推动机器人学习和开发。

## 项目简介

Newton 基于 NVIDIA Warp 构建，使机器人能够以更高的精度学习处理复杂任务。它与 MuJoCo Playground 或 NVIDIA Isaac Lab 等学习框架兼容。

- **GitHub**: [https://github.com/newton-physics/newton](https://github.com/newton-physics/newton)
- **官方博客**: [NVIDIA 技术博客](https://developer.nvidia.cn/blog/announcing-newton-an-open-source-physics-engine-for-robotics-simulation/)

## 核心特性

### 1. 开源

Newton 是完全开源的，为整个机器人社区提供了强大的支持。这使得机器人专家能够自由地使用和分发该框架，并为其发展贡献前沿研究成果。

### 2. NVIDIA 加速

Newton 基于 NVIDIA Warp 构建，这是一个 NVIDIA CUDA-X 加速库，使开发者能够轻松编写 GPU 加速、基于内核的程序，用于仿真 AI、机器人和机器学习。

利用 NVIDIA GPU 的并行处理能力，提供了一个高性能、灵活的框架，用于构建和运行基于物理的仿真。

### 3. MuJoCo-Warp 支持

Google DeepMind 首次推出了由 Warp 加速的开源机器人仿真器 MuJoCo-Warp。它使开发人员能够实现显著的性能提升：

- 人形机器人仿真：70 倍以上的提速
- 手动操作任务：100 倍的提速

### 4. 可微物理

通过仿真传播梯度的能力，为机器人仿真和学习开辟了新的可能性：

```python
import warp as wp
import newton

# 初始化
wp.init()

# 创建可微仿真场景
scene = newton.Scene()
scene.add_robot(urdf_path="robot.urdf")

# 前向仿真
with wp.Tape() as tape:
    state = scene.forward(action)
    
# 反向传播梯度
tape.backward(loss)
```

### 5. 高度可扩展

Newton 具有高度可扩展性，能够实现丰富的多物理场仿真：

- 自定义求解器和积分器
- 布料、流体等可变形物体仿真
- 材料点方法 (MPM) 求解器
- 多求解器混合（刚体 + 可变形体）

```python
# 自定义求解器示例
class MySolver(newton.Solver):
    def solve(self, state, dt):
        # 自定义求解逻辑
        pass

scene.add_solver(MySolver())
```

### 6. 基于 OpenUSD 构建

Newton 使用 OpenUSD 框架，灵活的数据模型和合成引擎聚合了用于描述机器人及其周围环境所需的数据。

## 架构图

```
┌─────────────────────────────────────────────────────────┐
│                    应用层 (Applications)                │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │
│  │ Isaac Lab   │  │ MuJoCo      │  │ 自定义应用   │    │
│  └─────────────┘  └─────────────┘  └─────────────┘    │
├─────────────────────────────────────────────────────────┤
│                    Newton 物理引擎                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌───────┐ │
│  │ 刚体求解器 │  │ MPM求解器 │  │ 可微物理  │  │ NeRD  │ │
│  └──────────┘  └──────────┘  └──────────┘  └───────┘ │
├─────────────────────────────────────────────────────────┤
│                    NVIDIA Warp                         │
│              (CUDA 加速的 Python 框架)                  │
└─────────────────────────────────────────────────────────┘
```

## 合作伙伴

| 合作伙伴 | 贡献 |
|---------|------|
| **NVIDIA** | Warp 框架、GPU 加速、NeRD 神经动力学 |
| **Google DeepMind** | MuJoCo-Warp 高性能物理引擎 |
| **Disney Research** | OpenUSD 集成、娱乐机器人平台 |

## 应用场景

### 1. 人形机器人仿真

Disney Research 将率先使用 Newton 推动其机器人角色平台发展，为下一代娱乐机器人提供支持。比如 GTC 主题演讲中和黄仁勋一起登台、以星球大战为灵感设计的富有表现力的 BDX 机器人。

### 2. 机器人策略学习

与 Isaac Lab 集成，为机器人学习提供高性能仿真后端：

```python
from isaaclab.app import AppLauncher
from isaaclab.envs import ManagerBasedRLEnv

# 使用 Newton 物理后端
env = ManagerBasedRLEnv(
    cfg=env_cfg,
    physics_backend="newton"
)
```

### 3. 可变形物体操作

支持布料、颗粒材料、软体等复杂物体的仿真：

```python
# 添加布料物体
scene.add_cloth(
    vertices=cloth_verts,
    indices=cloth_indices,
    stiffness=1000.0,
    damping=10.0
)

# 添加颗粒材料
scene.add_mpm(
    particles=sand_particles,
    material="sand",
    resolution=64
)
```

## 快速开始

### 安装

```bash
# 克隆仓库
git clone https://github.com/newton-physics/newton.git
cd newton

# 安装依赖
pip install warp-lang
pip install torch

# 安装 Newton
pip install -e .
```

### 基本使用

```python
import warp as wp
import newton

# 初始化 Warp
wp.init()

# 创建仿真场景
scene = newton.Scene(device="cuda:0")

# 添加机器人
scene.add_robot(
    urdf_path="ur5e.urdf",
    base_pos=(0.0, 0.0, 0.0)
)

# 添加地面
scene.add_ground()

# 仿真循环
for i in range(1000):
    # 设置控制命令
    scene.set_joint_positions(target_pos)
    
    # 步进仿真
    scene.step(dt=1/60.0)
    
    # 获取状态
    state = scene.get_state()
```

### 可微物理示例

```python
import warp as wp
import torch

wp.init()

# 创建可微场景
scene = newton.DifferentiableScene(device="cuda:0")
scene.add_robot("ur5e.urdf")

# 优化目标
target_pos = torch.tensor([0.5, 0.0, 0.5], device="cuda")

# 优化器
optimizer = torch.optim.Adam([scene.parameters], lr=0.01)

# 优化循环
for epoch in range(100):
    optimizer.zero_grad()
    
    # 前向仿真
    final_state = scene.rollout(initial_state, actions)
    
    # 计算损失
    loss = torch.norm(final_state.end_effector_pos - target_pos)
    
    # 反向传播
    loss.backward()
    optimizer.step()
    
    print(f"Epoch {epoch}, Loss: {loss.item():.4f}")
```

## 与 NeRD 集成

Newton 支持 NeRD (Neural Robot Dynamics) 作为后端求解器：

```python
from newton.nerd import NeuralDynamicsModel

# 加载预训练的 NeRD 模型
nerd_model = NeuralDynamicsModel(
    robot="ur5e",
    checkpoint="nerd_ur5e.pt"
)

# 设置为仿真后端
scene.set_solver(nerd_model)
```

## 性能基准

| 任务 | 传统 CPU | MuJoCo-Warp (GPU) | 提升倍数 |
|-----|---------|-------------------|---------|
| 人形机器人仿真 | 1x | 70x+ | 70 倍 |
| 手动操作任务 | 1x | 100x+ | 100 倍 |
| 可微仿真梯度 | - | - | 支持 |


