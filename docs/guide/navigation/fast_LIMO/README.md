# fast_LIMO

一个紧耦合实时激光雷达-惯性SLAM算法，基于LIMO-Velo和FAST_LIO项目开发。

## 项目链接

- GitHub: <https://github.com/fetty31/fast_LIMO>

## 项目概述

## 项目介绍
fast_LIMO是一款紧耦合、实时的LiDAR-Inertial SLAM算法，基于LIMO-Velo和FAST_LIO项目开发，依托IKFoM C++库实现。它采用多线程架构，仅依赖Eigen3和PCL库，可无需修改直接脱离ROS框架使用，同时也提供了ROS包装器。当前已支持通过KISS-Matcher实现基于保存的pcd地图的重定位，后续还计划添加回环检测功能。该算法可在高速、大转角的复杂场景下稳定运行，适配Formula Student赛车、KITTI数据集等多种测试环境。

## 主要特性
1.  实时紧耦合激光惯性SLAM方案
2.  基于C++开发，线程安全，依赖轻量化，可跨框架使用
3.  支持基于KISS-Matcher的地图重定位
4.  适配高速运动、狭窄弯道等复杂动态场景
5.  继承自LIMO-Velo与FAST_LIO等优秀算法的技术架构
