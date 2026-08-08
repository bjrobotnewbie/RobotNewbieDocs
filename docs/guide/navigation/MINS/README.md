# MINS

具备在线标定功能的高效且鲁棒的多传感器辅助惯性导航系统，能够融合惯性测量单元（IMU）、摄像头、激光雷达（LiDAR）、GPS/全球导航卫星系统（GNSS）以及轮速传感器。应用场景包括：VINS/VIO、GPS-INS、LINS/LIO，以及多传感器融合用于定位与建图（SLAM）。本仓库还提供多传感器仿真与数据支持。

## 项目链接

- GitHub: <https://github.com/rpng/MINS>

## 项目概述

An efficient, robust, and tightly-coupled **Multisensor-aided Inertial Navigation System (MINS)** which is capable of

flexibly fusing all five sensing modalities (**IMU**, **wheel** **encoders**, **camera**, **GNSS**, and **LiDAR**) in a filtering

fashion by overcoming the hurdles of computational complexity, sensor asynchronicity, and intra-sensor calibration.
Exemplary use case of MINS:
* VINS (mono, stereo, multi-cam)
* GPS-IMU (single, multiple)
* LiDAR-IMU (single, multiple)
* wheel-IMU
