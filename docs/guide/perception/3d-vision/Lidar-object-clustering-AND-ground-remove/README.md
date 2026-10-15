# Lidar-object-clustering-AND-ground-remove

激光雷达障碍物检测与聚类，参考论文：Efficient Online Segmentation for Sparse 3D Laser Scans；其中包含地面分割代码 ransac。

## 项目链接

- GitHub: <https://github.com/lonlonago/Lidar-object-clustering-AND-ground-remove>

## 项目介绍
本项目是基于ROS相关技术实现的激光雷达障碍物检测与聚类工具，参考论文《Efficient Online Segmentation for Sparse 3D Laser Scans》开发，包含基于my_ransac的地面分割代码，可直接运行`image_range_cluster_v2.py`启动，依赖numpy和python-pcl（无需可视化可省略）。

## 主要特性
1. 实现激光雷达点云的地面分割与障碍物聚类功能
2. 参考论文算法，针对稀疏3D激光扫描做在线分割处理
3. 提供可直接运行的Python脚本，依赖配置简单

目前存在待优化点：运行时间较长（约2s，论文要求20ms）、目标聚类效果待提升、RANSAC地面分割存在特殊场景问题、需添加目标立体框及尺寸计算功能。
