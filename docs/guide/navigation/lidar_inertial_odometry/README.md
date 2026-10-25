# lidar_inertial_odometry

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/lidar_inertial_odometry/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

紧耦合激光 - 惯性里程计

## 项目链接

- GitHub: <https://github.com/93won/lidar_inertial_odometry>

## 项目介绍
本项目是一款紧耦合激光惯性里程计（Tightly-Coupled Lidar-Inertial Odometry），基于Surfel-LIO算法实现，依托ROS生态开发，提供了快速部署的快速上手指南，同时附带ROS 2封装仓库。项目基于两篇顶会顶刊论文技术，可实现高精度的激光与惯性测量单元融合位姿估计。

## 主要特性
1.  采用紧耦合融合方案，充分利用激光与IMU数据的互补信息提升位姿估计精度
2.  基于预计算Surfel（面元）与分层Z序体素哈希实现高效建图与状态估计
3.  引入概率核优化算法提升复杂场景下的状态估计鲁棒性
4.  提供完整的安装与数据集使用教程，附带演示视频，支持快速验证功能。
