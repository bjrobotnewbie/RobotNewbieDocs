# PositionBasedDynamics

PositionBasedDynamics 是一个基于物理的刚性体、变形固体和流体仿真库。

## 项目链接

- GitHub: <https://github.com/InteractiveComputerGraphics/PositionBasedDynamics>

## 项目介绍
PositionBasedDynamics是一款用于刚体、可变形固体以及流体物理模拟的开源库，基于位置动力学（Position-Based Dynamics）方法实现。该类模拟方法直接通过准静态问题求解计算每一步的位置变化，具备速度快、稳定性强、易控的特点，适合交互式场景，主要应用于VR、电脑游戏以及影视广告特效制作领域，仅提供视觉上的物理真实性。

## 主要特性
1.  支持多种约束的位置式物理模拟，可处理刚体、可变形固体和流体
2.  依赖CMake、Eigen、json、pybind11等外部库，所有依赖均已内置，还自研Discregrid库用于生成立方有符号距离场实现碰撞检测
3.  提供Python接口pyPBD，支持跨平台编译（Linux、Windows），附带完整文档
4.  可用于刚体-流体耦合模拟，已被SPlisHSPlasH流体模拟器采用
