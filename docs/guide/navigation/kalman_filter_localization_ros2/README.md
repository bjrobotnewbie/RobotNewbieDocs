# kalman_filter_localization_ros2

基于卡尔曼滤波的gnss/imu定位

## 项目链接

- GitHub: <https://github.com/rsasaki0109/kalman_filter_localization_ros2>

## 项目概述

## 项目介绍
这是一款面向ROS 2的GNSS/IMU/里程计融合定位工具，基于误差状态扩展卡尔曼滤波（Error-state EKF）实现，可估算载体的位置、速度、姿态以及IMU零偏，支持多传感器输入的组合定位。

## 主要特性
1.  支持GNSS位姿、`NavSatFix`和多普勒速度输入
2.  可估算陀螺仪和加速度计零偏
3.  内置GNSS NIS门控过滤和Huber/Cauchy鲁棒损失函数
4.  支持GNSS天线杆臂补偿和短时延迟修正
5.  可选接入轮速计、NHC、ZUPT、ZIHR辅助定位
6.  采用连续时间过程噪声和二阶离散化算法
7.  提供CSV结果评估和UrbanNav Tokyo数据集 ablation测试工具

同时提供了完整的编译运行教程、话题接口说明、GNSS输入配置方式以及定位结果评估脚本，适配UrbanNav东京数据集的测试流程。
