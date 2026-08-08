# gym-pybullet-drones

- 项目链接：https://github.com/learnsyslab/gym-pybullet-drones
论文链接：https://arxiv.org/pdf/2103.02142

## 项目概述
gym-pybullet-drones是一个基于PyBullet的Gymnasium环境，专为四旋翼飞行器的多智能体强化学习研究设计。核心特点包括：
1. 采用简单易用的OpenAI Gym风格接口，支持快速开发和验证强化学习算法
2. 基于PyBullet的高精度物理仿真，支持多智能体编队飞行等复杂场景
3. 默认集成Bitcraze Crazyflie 2.x纳米四旋翼的动力学模型，贴近真实硬件
4. 提供稳定的版本分支，建议使用main分支获取最新功能和bug修复
5. 支持安全控制、强化学习、多机器人系统等多个研究领域

该环境是机器人控制和强化学习研究的常用工具，能够帮助开发者快速验证无人机控制算法和多智能体协同策略。