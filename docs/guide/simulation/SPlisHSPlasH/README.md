# SPlisHSPlasH

SPlisHSPlasH 是一个开源库，用于物理基础模拟流体。

## 项目链接

- GitHub: <https://github.com/InteractiveComputerGraphics/SPlisHSPlasH>
- 项目主页: <https://splishsplash.physics-simulation.org/>

## 项目介绍
SPlisHSPlasH是一款开源的基于物理的流体模拟库，核心基于光滑粒子流体动力学（SPH）这一经典无网格拉格朗日方法，可高效模拟复杂流体效果。它支持跨平台编译，覆盖Linux、Windows、macOS系统，附带完整文档。

## 主要特性
1.  实现了WCSPH、PCISPH、PBF、IISPH、DFSPH、PF等多款当前主流的不可压缩流体压力求解器
2.  提供粘度、表面张力、涡旋等多种流体物理效果模拟方法
3.  集成了PositionBasedDynamics、Discregrid、CompactNSearch等自研库，可实现刚体动力学模拟、刚体碰撞检测以及高效邻域搜索
4.  内置所有依赖的外部库，包括Eigen、json、pybind11、imgui等，开箱即用
