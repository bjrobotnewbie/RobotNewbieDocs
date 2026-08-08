# Tinfour

基于Java实现的Delaunay三角剖分与约束Delaunay三角剖分，提供高性能工具用于曲面建模，支持激光雷达LAS文件、数字高程模型（DEM）、有限元分析、路径规划、自然邻点插值，以及不规则三角网（TIN）的其他应用场景。

## 项目链接

- GitHub: <https://github.com/gwlucastrig/Tinfour>

## 项目概述

## 项目介绍
Tinfour是一款Java编写的高性能Delaunay三角剖分工具库，用于构建和应用符合Delaunay准则的不规则三角网（TIN）。它可处理大规模数据集，在普通笔记本上每秒可处理超百万个采样点，支持Lidar LAS文件、数字高程模型（DEM）、有限元分析、路径规划、自然邻域插值等TIN相关应用。

## 主要特性
1.  实现高性能2D Delaunay及约束Delaunay三角剖分
2.  针对大数据集优化性能与内存占用
3.  提供丰富的TIN建模工具，支持多种工程与科研场景
4.  附带演示程序Tinfour Viewer，可直观体验库的核心功能
5.  包含详尽的代码注释与算法说明文档，支持二次开发

项目编译后的Jar包可通过Maven中央仓库获取，另有.NET移植版本Tinfour.NET可供使用。
