# robot_calibration

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/robot_calibration/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

机器人通用标定

## 项目链接

- GitHub: <https://github.com/mikeferguson/robot_calibration>

## 项目介绍
这是一个ROS2通用机器人标定工具包，提供多个ROS2节点，用于校准机器人的多项参数，包括3D相机内外参、关节角度偏移、机器人坐标系偏移，还支持移动底盘相关参数调校与磁力计硬铁校准。
其中核心节点`calibrate`通过两步完成标定：先采集机器人关节位置与传感器观测数据，再通过优化算法最小化重投影误差，最终将标定参数更新到URDF或相机配置YAML文件中。

## 主要特性
1.  支持多类型机器人参数标定，覆盖相机、关节、底盘、磁力计等多维度校准需求
2.  采用数据采集+误差优化的两步标定流程，适配手动/自动采集标定位姿
3.  配置通过YAML文件管理，兼容ROS2生态，可快速集成到现有机器人项目中。
