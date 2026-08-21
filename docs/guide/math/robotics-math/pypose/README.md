# pypose

基于不同iable 的机器人学库。

## 项目链接

- GitHub: <https://github.com/pypose/pypose>
- 项目主页: <https://pypose.org>

## 项目概述

## 项目介绍
PyPose是一个面向机器人领域、基于PyTorch的可微机器人流形库，旨在结合深度学习感知模型与基于物理的优化技术，弥补纯数据驱动深度学习在泛化性上的不足，以及纯物理优化在复杂任务上的性能短板。该库设计目标为易用、高效、可解释，采用命令式风格接口，可便捷集成到实际机器人应用中。

## 主要特性
1.  **LieTensor模块**：支持SO3、SE3、Sim3、RxSO3等李群以及对应李代数的运算
2.  **功能模块**：涵盖LTI/LTV系统建模、EKF/UKF/PF滤波、EPnP位姿求解、LQR控制器、IMU预积分等机器人常用工具
3.  **二阶优化器**：内置GaussNewton、LevenbergMarquardt等物理优化常用求解器
4.  支持李群/李代数雅可比并行计算，具备高效计算能力
