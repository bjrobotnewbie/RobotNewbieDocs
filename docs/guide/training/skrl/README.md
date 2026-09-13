# skrl

模块化强化学习（RL）库（基于 PyTorch、JAX 和 NVIDIA Warp 实现，支持 Gymnasium/Gym、NVIDIA Isaac Lab、MuJoCo Playground 及其他环境）

## 项目链接

- GitHub: <https://github.com/Toni-SM/skrl>
- 项目主页: <https://skrl.readthedocs.io/>

## 项目介绍
skrl是一款开源模块化强化学习（RL）Python库，支持PyTorch、JAX和NVIDIA Warp三种后端实现，核心设计目标为模块化、高可读性、简洁性与算法实现透明化。

该库兼容Gym、Gymnasium、PettingZoo、ManiSkill等多种环境接口，同时支持加载配置NVIDIA Isaac Lab与MuJoCo Playground环境，支持在同一次运行中按作用域（环境子集）同时训练智能体，子集间可共享或独立使用资源。

## 主要特性
1.  多后端支持：覆盖PyTorch、JAX、NVIDIA Warp
2.  广泛环境兼容：支持主流强化学习环境以及NVIDIA Isaac Lab、MuJoCo Playground等仿真环境
3.  模块化设计，算法实现清晰透明，便于二次开发与调试
4.  支持按环境作用域批量训练智能体
5.  提供完整文档与示例，项目处于持续活跃开发中
