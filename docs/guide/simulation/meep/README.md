# meep

用于电磁仿真的免费有限差分时域（FDTD）软件

## 项目链接

- GitHub: <https://github.com/NanoComp/meep>

## 项目介绍
Meep是一款免费开源的电磁仿真FDTD（有限差分时域）软件包，可用于多场景下的电磁学模拟，支持Linux、macOS、FreeBSD等类Unix系统，提供Conda预编译二进制包，兼容Python、Scheme、C++三种API。

## 主要特性
1.  遵循GNU GPL开源协议
2.  支持1d、2d、3d及圆柱坐标系仿真，可利用对称性缩减计算量
3.  支持MPI分布式并行计算
4.  支持多种自定义材料：各向异性/色散/非线性/导电/饱和增益/旋磁介质等，内置标准材料库
5.  提供PML吸收边界、Bloch周期边界、理想导体边界条件，支持亚像素平滑提升精度
6.  多API脚本化开发，提供完整官方文档与教程
