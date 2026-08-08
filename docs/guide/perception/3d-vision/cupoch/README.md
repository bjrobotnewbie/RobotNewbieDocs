# cupoch

基于GPU计算的机器人技术

## 项目链接

- GitHub: <https://github.com/neka-nat/cupoch>

## 项目概述

## 项目介绍
Cupoch是一款基于CUDA的机器人3D数据快速处理库，依托Open3D开发，旨在为机器人系统提供高速3D数据计算能力，可应用于SLAM、避障、路径规划、目标跟踪等机器人相关场景。

## 主要特性
1.  基于CUDA加速的3D数据处理与机器人计算：
    - 支持KNN查询（基于LBVH优化及FLANN）
    - 多种点云配准算法：ICP、广义ICP、对称ICP、彩色点云配准、快速全局配准、FilterReg
    - 点云特征提取：FPFH、SHOT
    - 点云关键点检测：ISS
    - 基于GPU加速的G-DBSCAN点云聚类
    - 点云/三角网格滤波、下采样
    - 数据IO功能
