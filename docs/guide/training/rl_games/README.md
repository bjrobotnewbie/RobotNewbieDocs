# rl_games

rl_games 是高性能强化学习算法库，重点支持 PPO、GPU 加速仿真训练和机器人控制任务。

## 项目链接

- GitHub: <https://github.com/Denys88/rl_games>

## 项目概述

rl_games 是一个以 PyTorch 为核心的强化学习实现库，长期用于 Isaac Gym、Brax、MuJoCo、DeepMind Control、StarCraft 多智能体等环境中的高吞吐训练。项目支持 PPO、非对称 actor-critic、masked actions、多智能体训练、自博弈以及端到端 GPU 加速训练流程，尤其适合需要大量并行环境的机器人和控制任务。

README 中展示了多种基于 GPU 仿真的机器人学习成果，例如四足/人形运动、灵巧手操作、TriFinger 迁移和 AMP 等。对机器人强化学习用户来说，rl_games 的价值在于提供经过实践验证的高性能训练循环和配置方式，可与 Isaac Gym/Isaac Lab 等仿真平台组合进行大规模策略训练。
