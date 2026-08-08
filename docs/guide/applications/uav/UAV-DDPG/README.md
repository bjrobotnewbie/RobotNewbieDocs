# UAV-DDPG

论文《无人机辅助移动边缘计算中的计算卸载优化：一种深度确定性策略梯度方法》的代码

## 项目链接

- GitHub: <https://github.com/fangvv/UAV-DDPG>
- 项目主页: https://fangvv.github.io/Homepage/Edgecomp/

## 项目概述

## 项目介绍
本项目是论文《Computation Offloading Optimization for UAV-assisted Mobile Edge Computing: A Deep Deterministic Policy Gradient Approach》的开源代码，针对无人机辅助移动边缘计算（MEC）系统的计算卸载优化问题展开研究。
该系统中，配备计算资源的UAV可为附近用户设备（UE）提供任务卸载服务，UE将部分计算任务卸载至UAV，剩余任务本地执行。研究目标是在离散变量与能耗约束下，通过联合优化用户调度、任务卸载比例、UAV飞行角度和速度，最小化最大处理延迟。针对问题非凸性、高维状态空间与连续动作空间，项目基于强化学习（RL）中的深度确定性策略梯度（DDPG）算法实现最优卸载策略，可在动态环境中快速收敛并获得优于DQN等基线算法的延迟优化效果。

## 主要特性
1.  实现了基于DDPG的UAV辅助MEC计算卸载优化算法
2.  包含完整的UAV、UE、信道与能耗环境模拟器
3.  提供状态归一化、探索噪声等 ablation 实验模块
4.  附带DQN基线算法实现用于对比实验
5.  依赖TensorFlow 1.X、NumPy、Matplotlib工具库
