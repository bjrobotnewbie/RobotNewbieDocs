# pyRANSAC-3D

一个用于在点云中使用 RANSAC 算法拟合三维形状的 Python 工具

## 项目链接

- GitHub: <https://github.com/leomariga/pyRANSAC-3D>
- 项目主页: <https://leomariga.github.io/pyRANSAC-3D/>

## 项目概述

## 项目介绍
pyRANSAC-3D是一个开源的RANSAC算法Python实现工具，可在点云中拟合平面、圆柱、长方体、球体、直线、圆形等基础3D形状，适用于3D SLAM、3D重建、物体追踪等场景。

## 主要特性
1.  支持拟合多种基础3D几何体：平面、圆柱、长方体、球体、直线、圆形、点集
2.  依赖仅为Numpy，可通过PyPI快速安装
3.  提供简洁易用的API接口，附带完整使用示例
4.  可处理带噪声的点云数据，输出拟合结果与内点索引
