# pytorch_volumetric

在PyTorch中实现的体素、SDF等体积结构

## 项目链接

- GitHub: <https://github.com/UM-ARM-Lab/pytorch_volumetric>

## 项目概述

## 项目介绍
本项目是基于PyTorch实现的体素、有符号距离场（SDF）等体积结构工具库，支持并行化的SDF值与梯度查询、自动扩容范围的体素网格、单向 chamfer 距离计算，以及支持多配置并行查询的机器人模型转SDF功能，可用于机器人感知、仿真等场景。

## 主要特性
1.  实现并行化查询的PyTorch版SDF，支持值与梯度计算
2.  支持自动扩容范围的体素网格
3.  提供单向点到网格chamfer距离计算
4.  支持将机器人模型转换为SDF，并可并行查询多配置与多点数据
5.  性能优异：基于RTX3090与Apple M3 Max的基准测试显示，CachedSDF相比原生MeshSDF可获得22-130倍加速，100K点查询仅需0.70ms（GPU）/2.6ms（CPU）
6.  支持通过pip快速安装，提供完整测试样例与基准测试脚本
