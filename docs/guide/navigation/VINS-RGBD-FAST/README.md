# VINS-RGBD-FAST

VINS-RGBD-FAST 是一个基于 VINS-RGBD 的 SLAM 系统。我们对系统进行了一些优化，以加速其在资源受限的嵌入式平台上的性能，例如华为 Atlas 200DK、Raspberry Pi 等。

## 项目链接

- GitHub: <https://github.com/jianhengLiu/VINS-RGBD-FAST>

## 项目介绍
VINS-RGBD-FAST是一款基于VINS-RGBD的RGBD惯性SLAM系统，针对华为Atlas 200DK、NVIDIA Jetson AGX Xavier等资源受限嵌入式平台做了性能优化，可应用于小型地面救援机器人、手持设备、轮式机器人的轨迹估计与建图，适配动态环境。项目基于VINS-Mono开发，支持深度集成的视觉惯性初始化、带深度信息的视觉惯性里程计，可生成适用于路径规划导航的去噪地图。

## 主要特性
1.  采用基于网格的FAST特征检测替代原Harris特征
2.  新增静止状态初始化、IMU辅助特征跟踪、提取特征区域质量判断
3.  解决FAST特征导致的特征聚类问题
4.  支持`sensor_msg::CompressedImage`压缩图像话题格式
5.  适配Ubuntu 16.04/18.04 + ROS Kinetic/Melodic环境，可部署在嵌入式边缘平台。
