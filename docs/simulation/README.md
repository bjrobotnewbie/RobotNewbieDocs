# 仿真与模拟

仿真与模拟技术是机器人开发过程中的重要工具，可以在虚拟环境中测试机器人算法、控制策略和系统性能，无需实际硬件，大大降低开发成本和风险。本章节涵盖主流的仿真与模拟工具和技术。

## 项目列表

- [CoppeliaSim](simulation/coppeliasim/README.md)
- [Bullet Physics SDK](simulation/bullet-physics/README.md)
- [DART](simulation/dart/README.md)
- [Drake](simulation/drake/README.md)
- [Gazebo](simulation/gazebo/README.md)
- [Genesis](simulation/genesis/README.md)
- [GenieSim](simulation/geniesim/README.md)
- [Habitat Sim](simulation/habitat-sim/README.md)
- [Internutopia](simulation/internutopia/README.md)
- [Isaac Gym](simulation/isaacgym/README.md)
- [Isaac Sim](simulation/isaacsim/README.md)
- [MuJoCo](simulation/mujoco/README.md)
- [PyBullet](simulation/pybullet/README.md)
- [Sapien](simulation/sapien/README.md)
- [SOFA](simulation/sofa/README.md)
- [NeRD](simulation/nerd/README.md)
- [Newton](simulation/newton/README.md)

## 分类说明

| 分类          | 核心特点                             | 适用场景              |
| ----------- | -------------------------------- | ----------------- |
| **通用仿真**    | CoppeliaSim, Gazebo, PyBullet    | 多机器人系统，算法快速验证     |
| **物理仿真**    | MuJoCo, Isaac Gym, SOFA          | 高精度物理交互，接触力学仿真    |
| **具身智能仿真**  | Habitat Sim, Isaac Sim, GenieSim | 视觉导航，具身AI研究       |
| **工业仿真**    | Sapien, Genesis                  | 工业机器人，装配任务仿真      |
| **神经动力学仿真** | NeRD, Newton                     | 可微物理，GPU 加速，端到端学习 |

