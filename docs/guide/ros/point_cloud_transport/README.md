# point_cloud_transport

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/point_cloud_transport/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

点云压缩：ROS

## 项目链接

- GitHub: <https://github.com/ros-perception/point_cloud_transport>
- 项目主页: <https://docs.ros.org/en/rolling/p/point_cloud_transport>

## 项目介绍
这是一个ROS2软件包，用于通过多种传输层发布和订阅PointCloud2消息，主打低带宽场景下的点云数据传输，可借助Google Draco压缩库实现点云压缩，适配ROS2全系列主流发行版。

## 主要特性
1.  兼容ROS2生态，支持Rolling、Lyrical、Kilted、Jazzy、Humble等多个发行版
2.  提供标准化的点云传输接口，可切换不同压缩/传输策略
3.  内置Draco点云压缩能力，可降低低带宽网络下的传输开销
4.  提供二进制包支持，部署便捷
