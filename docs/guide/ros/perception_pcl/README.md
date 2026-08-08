# perception_pcl

perception_pcl 是 Point Cloud Library 在 ROS 中的接口栈，用于点云和三维几何处理应用。

## 项目链接

- GitHub: <https://github.com/ros-perception/perception_pcl>
- 项目主页: http://wiki.ros.org/perception_pcl

## 项目概述

perception_pcl 将 PCL 与 ROS 生态连接起来，是 ROS 中处理 n 维点云和三维几何数据的常用桥接层。它让机器人系统可以在 ROS topic、message 和 node 管线中使用 PCL 的滤波、分割、特征、配准和几何处理能力。

该仓库内容简洁，但在 ROS 感知生态中具有基础作用。对于使用激光雷达、深度相机、RGB-D 传感器或三维重建数据的机器人项目，perception_pcl 通常作为点云处理链路的一部分，与 sensor_msgs、pcl_conversions、pcl_ros 和下游定位/建图/识别模块配合使用。
