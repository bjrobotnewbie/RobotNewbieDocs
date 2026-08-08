# ros2-depth-anything-v3-trt

基于Depth Anything V3、用于从相机图像进行单眼度量深度估计与点云生成的ROS2 TensorRT节点

## 项目链接

- GitHub: <https://github.com/ika-rwth-aachen/ros2-depth-anything-v3-trt>

## 项目概述

## 项目介绍
本项目是基于ROS 2的TensorRT节点，通过Depth Anything V3实现单目度量深度估计与点云生成。它订阅相机图像和相机标定信息话题，可实时输出度量深度图与`PointCloud2`格式点云，由亚琛工业大学汽车工程研究所（ika）开源维护。

## 主要特性
1.  借助TensorRT加速，实现Depth Anything V3实时度量深度估计
2.  可从深度图直接生成点云
3.  支持带配色方案的调试可视化
4.  可配置FP16/FP32推理精度
5.  支持标准ROS话题输入输出，兼容`image_transport`压缩图像传输
