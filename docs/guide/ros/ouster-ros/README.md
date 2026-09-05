# ouster-ros

官方 ROS 驱动：Ouster 传感器（OS0、OS1、OS2、OS Dome）

## 项目链接

- GitHub: <https://github.com/ouster-lidar/ouster-ros>
- 项目主页: <https://ouster.com>

## 项目介绍
本项目是Ouster传感器的官方ROS驱动包，支持ROS1和ROS2版本，适配FW v2.0及以上的OS0、OS1、OS2、OSDome系列激光雷达传感器。
驱动启动后会自动配置并连接目标传感器，接收并解析IMU与激光数据包，发布`/ouster/imu`话题的IMU数据、`/ouster/points`话题的点云数据，若传感器开启双返回模式，还会额外发布`/ouster/points2`话题的第二点云数据。支持传感器模式、录制模式、重放模式以及实验性组播模式三种运行方式。

## 主要特性
1.  官方出品，兼容性有保障，适配全系列Ouster激光雷达传感器
2.  同时支持ROS1（melodic/noetic）与ROS2（foxy/galactic/humble/iron/jazzy/rolling）版本
3.  支持多种运行模式，可直接连接传感器、录制数据包或重放PCAP文件
4.  自动解析传感器数据并输出标准ROS话题消息，支持双返回点云输出
5.  提供服务调用接口，可获取、配置传感器参数
