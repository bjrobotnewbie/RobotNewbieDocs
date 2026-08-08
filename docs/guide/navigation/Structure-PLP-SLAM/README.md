# Structure-PLP-SLAM

[ICRA'23] 结构 PLP-SLAM：基于点、线和平面的高效稀疏地图构建与定位——面向单目、RGB-D 和立体相机的实现

## 项目链接

- GitHub: <https://github.com/PeterFWS/Structure-PLP-SLAM>

## 项目概述

## 项目介绍
本项目是ICRA 2023论文《Structure PLP-SLAM: Efficient Sparse Mapping and Localization using Point, Line and Plane for Monocular, RGB-D and Stereo Cameras》的官方实现，是一款支持单目、RGB-D、双目相机的视觉SLAM系统，融合点、线、面三种视觉特征实现高效稀疏建图与定位。支持TUM RGB-D、ICL-NUIM、EuRoC MAV、KITTI等主流数据集测试。

## 主要特性
1.  支持三种视觉特征融合的SLAM方案，可适配多种相机类型
2.  基于PangolinViewer构建可视化界面，默认使用该查看器
3.  代码基于早期版本OpenVSLAM开发，配套对应版本官方文档
4.  内置ORB词袋模型，可直接使用；平面SLAM需提前完成图像分割预处理
5.  测试兼容Ubuntu 24.04系统，依赖OpenCV 3.4.16、Eigen3、g2o、DBoW2等库。
