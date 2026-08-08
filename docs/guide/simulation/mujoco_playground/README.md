# mujoco_playground

一个用于GPU加速机器人学习与仿真到真实迁移的开源库。

## 项目链接

- GitHub: <https://github.com/google-deepmind/mujoco_playground>
- 项目主页: https://playground.mujoco.org

## 项目概述

## 项目介绍
mujoco_playground 是谷歌DeepMind推出的开源GPU加速机器人学习与 sim-to-real 迁移工具库，基于MuJoCo MJX构建，为机器人学习研究提供全面的仿真环境套件。支持通过PyPI快速安装，也可从源码获取最新功能，适配Python 3.10及以上版本，可用于机器人控制、仿真到现实迁移等研究场景。

## 主要特性
1.  覆盖经典控制、 quadruped/bipedal 运动、非拟人/灵巧操作等多类仿真环境
2.  支持MJWarp批量渲染，可实现视觉相关的训练任务
3.  兼容MJX JAX与MuJoCo Warp两种仿真后端
4.  提供命令行快速训练入口，可一键启动PPO算法训练机器人任务
