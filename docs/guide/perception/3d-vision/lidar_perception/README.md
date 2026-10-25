# lidar_perception

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/lidar_perception/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

一个包含地面滤波、聚类、最小盒、跟踪和状态估计的激光雷达感知系统。

## 项目链接

- GitHub: <https://github.com/hehern/lidar_perception>

## 项目介绍
本项目是一款面向自动驾驶的激光雷达感知系统，支持基于urdf的坐标转换，集成了地面滤波、多种聚类算法（区域生长聚类、欧几里得聚类、2D DBSCAN聚类）、minbox目标框拟合、hm_tracker目标跟踪以及状态估计功能。

## 主要特性
1.  覆盖激光雷达感知全流程核心模块
2.  提供多种主流点云聚类方案适配不同场景
3.  支持通过urdf完成坐标转换
4.  集成目标跟踪与状态估计能力，可输出完整感知结果
