# vamp

SIMD加速的基于采样的运动规划

## 项目链接

- GitHub: <https://github.com/KavrakiLab/vamp>

## 项目概述

## 项目介绍
Vector-Accelerated Motion Planning（VAMP）是一个基于SIMD加速的采样式运动规划库，支持多种经典及前沿运动规划算法，可用于机器人路径规划场景。它通过CPU SIMD指令加速碰撞检测与正运动学计算，在消费级桌面PC单核心上，针对Franka Emika Panda机械臂的MotionBenchMaker数据集规划任务， median速度可达35微秒，同时也可在ARM低功耗设备上运行。

## 主要特性
1.  实现了ICRA 2024、RSS 2024、ICRA 2025等顶会顶刊的多款规划算法，包括RRT-Connect、PRM、Collision-Affording Point Trees(CAPT)、Fully Connected Informed Trees(FCIT*)、Asymptotically Optimal RRT-Connect(AORRTC)
2.  利用SIMD指令实现硬件加速的并行采样式规划，无需修改即可适配多种规划算法
3.  支持x86与ARM架构设备，提供Python包与交互式演示网页
4.  提供完整的构建、格式检查CI工作流，代码质量有保障
