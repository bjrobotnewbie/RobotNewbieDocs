# Air-IO

[IEEE RA-L] Air-IO: 面向无人机（UAV）的基于学习的IO框架

## 项目链接

- GitHub: <https://github.com/Air-IO/Air-IO>
- 项目主页: <https://air-io.github.io>

## 项目介绍
Air-IO是一款面向无人机的基于学习的惯性里程计（IO）框架，已被IEEE Robotics and Automation Letters (RA-L)收录。该框架聚焦于提升IMU特征可观测性，通过学习方法实现无人机的精准位姿估计，支持在EuRoC、Blackbird以及自研Pegasus仿真数据集上开展实验。

## 主要特性
1.  基于PyPose构建，依托学习方法优化IMU惯性里程计性能
2.  提供预训练模型与完整数据集下载，支持快速复现实验
3.  支持标准EKF推理模式，可直接使用真实方位输入快速测试网络效果
4.  适配多类公开无人机数据集与自研仿真数据集，覆盖不同测试场景
