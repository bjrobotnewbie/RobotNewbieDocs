# JamBoy

GPS 剥夺下的无人机导航层：光流 + 离线地图配准 + EKF → MAVLink（仿真验证）。

## 项目链接

- GitHub: <https://github.com/Fratres-X-AI/JamBoy>
- 项目主页: <--disable-wiki>

## 项目概述

## 项目介绍
JamBoy是一款用于GPS拒止环境下的无人机导航层，通过光流、离线地图地理匹配、EKF融合与气压高度数据，输出MAVLink格式的位置估计，已通过仿真验证。它仅负责导航功能，非飞行认证软件，适用于可消耗型无人机在无GPS环境下的定位导航。

## 主要特性
1.  **核心功能**：基于向下摄像头、预加载GeoTIFF地图、IMU与气压计数据，无需GPS即可估算本地位置与速度
2.  **技术方案**：
    - 采用Lucas-Kanade光流结合陀螺仪去旋转计算地面速度
    - 可选ORB/SIFT特征结合RANSAC单应性匹配实现绝对地理定位
    - 6状态EKF融合气压高度数据
    - 内置巡航、死 reckoning、终端、中止状态机
    - 支持MAVLink `VISION_POSITION_ESTIMATE` 输出
3.  **兼容性**：支持全局快门摄像头，兼容卷帘快门；支持CPU/GPU运行环境，适配Python 3.10+
4.  **硬件支持**：提供通用部署清单、约250美元的COTS原型套件（树莓派5+IMX296摄像头+Pixhawk飞控）与硬件 tradeoff 分析文档。
