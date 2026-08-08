# Gymnasium-Robotics

## 资源简介

Gymnasium-Robotics 是由 Farama Foundation 开发的机器人仿真环境集合，专门用于强化学习研究。官方定义为"一个用于强化学习的机器人仿真环境集合"。它使用 MuJoCo 物理引擎和 maintained mujoco python bindings 提供高精度物理仿真。

## 官方链接

* GitHub仓库：<https://github.com/Farama-Foundation/Gymnasium-Robotics>
* 官方文档：<https://robotics.farama.org/>
* Gymnasium 主站：<https://gymnasium.farama.org/>

## 主要特点

* **标准化接口**：完全兼容 Gymnasium API
* **MuJoCo 物理引擎**：高精度物理仿真
* **丰富的机器人环境**：提供多种机器人平台和任务
* **开源免费**：BSD-3-Clause 许可证
* **易于扩展**：支持自定义机器人任务
* **多平台支持**：支持 Linux、macOS、Windows

## 核心环境

* **Fetch 系列**：机械臂抓取和搬运任务（FetchPickAndPlace、FetchPush 等）
* **Shadow Hand**：灵巧手操作任务，转动物体、精确放置
* **Franka 系列**：协作机器人操作任务
* **四足机器人**：运动控制任务

## 代码示例

```python
import gymnasium as gym
import gymnasium_robotics

gym.register_envs(gymnasium_robotics)

env = gym.make("FetchPickAndPlace-v3", render_mode="human")
observation, info = env.reset(seed=42)

for _ in range(1000):
    action = policy(observation)
    observation, reward, terminated, truncated, info = env.step(action)

    if terminated or truncated:
        observation, info = env.reset()

env.close()
```
