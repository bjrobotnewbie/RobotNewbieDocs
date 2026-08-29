# BIEVR-LIO

🦫 BIEVR-LIO：基于凸图像增强的 Voxel 地图的鲁棒激光雷达 - 惯性里程计（RSS 2026）

## 项目链接

- GitHub: <https://github.com/ethz-asl/BIEVR-LIO>
- 项目主页: <https://patripfr.github.io/bievr-lio/>

## 项目介绍
BIEVR-LIO是一款鲁棒的LiDAR-Inertial Odometry框架，已被RSS 2026收录。它通过凸点图像增强的体素地图，利用高分辨率体素定向高度图像来挖掘信息稀疏的复杂场景中的细微几何变化，可实现可靠的激光惯性里程计计算。该项目支持ROS1 Noetic、ROS2 Humble/Jazzy，适配Ubuntu 20.04/22.04/24.04环境。

## 主要特性
1.  采用体素定向高度图像地图，强化复杂稀疏场景下的几何特征提取
2.  支持多ROS版本与多Ubuntu系统环境，具备良好的兼容性
3.  针对信息匮乏的挑战性场景做了针对性优化，提升里程计鲁棒性
