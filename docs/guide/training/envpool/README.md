# envpool

基于C++开发、适用于通用RL环境的高性能并行环境执行引擎（向量化环境）

## 项目链接

- GitHub: <https://github.com/sail-sg/envpool>
- 项目主页: https://envpool.readthedocs.io

## 项目概述

## 项目介绍
EnvPool是一款基于C++开发的高性能并行环境执行引擎，通过pybind11和线程池实现批量环境管理，适配通用强化学习（RL）场景。它拥有出色的运行性能，在DGX-A100设备上，Atari游戏可达到约100万原始FPS，MuJoCo模拟器可达约300万原始FPS，同时兼容Gymnasium、dm_env等主流RL环境接口，支持同步/异步、单/多玩家环境。

## 主要特性
1.  高性能并行执行，支持超大规模环境同时运行
2.  兼容多类主流RL环境API
3.  已支持Atari游戏、MuJoCo、经典控制环境、DeepMind Control Suite、Google Research Football、Procgen等十余类常用RL训练环境
4.  提供同步、异步两种运行模式，适配单/多玩家场景
