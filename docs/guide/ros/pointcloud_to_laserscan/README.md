# pointcloud_to_laserscan

将 3D 点云转换为 2D 激光扫描。

## 项目链接

- GitHub: <https://github.com/ros-perception/pointcloud_to_laserscan>
- 项目主页: <http://wiki.ros.org/pointcloud_to_laserscan>

## 项目介绍
本项目是ROS 2生态下的功能包，为ROS 1同名包的移植版本，核心功能是实现`sensor_msgs/msg/PointCloud2`（点云）与`sensor_msgs/msg/LaserScan`（激光扫描）消息的双向转换，包含两个核心组件，分别完成点云转激光扫描、激光扫描转点云的任务。

## 主要特性
1. 提供`PointCloudToLaserScanNode`组件：订阅`cloud_in`话题的点云数据，可通过`min_height`/`max_height`等参数配置采样范围、扫描角度、距离阈值等，输出符合要求的激光扫描数据到`scan`话题，支持坐标帧变换。
2. 提供`LaserScanToPointCloudNode`组件：订阅`scan_in`话题的激光扫描数据，可配置坐标帧变换，输出对应点云数据到`cloud`话题。
3. 两个组件均支持通过参数配置队列大小、坐标变换容差等，且仅在对应输出话题存在订阅者时才处理输入数据，避免资源浪费。
