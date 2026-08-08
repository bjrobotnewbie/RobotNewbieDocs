# gtsam

GTSAM 是一个在机器人与视觉领域实现了平滑与建图（SAM）的 C++ 类库，它采用因子图和贝叶斯网络作为底层计算范式，而非稀疏矩阵。

## 项目链接

- GitHub: <https://github.com/borglab/gtsam>
- 项目主页: https://borglab.github.io/gtsam/

## 项目概述

## 项目介绍
GTSAM全称Georgia Tech Smoothing and Mapping Library，是一款C++类库，用于机器人与计算机视觉领域的平滑与建图（SAM），底层采用因子图和贝叶斯网络作为计算范式，而非稀疏矩阵。该库同时提供MATLAB和Python封装，支持Ubuntu、MacOS、Windows多平台编译，可通过PyPI获取开发版Python包。

## 主要特性
1.  基于因子图和贝叶斯网络实现机器人与视觉领域的平滑建图任务
2.  提供C++原生API，以及Python、MATLAB语言封装
3.  支持多主流操作系统和编译器，适配C++17开发计划，当前4.2版本为稳定版
4.  可通过标准CMake流程完成编译安装，附带单元测试校验
