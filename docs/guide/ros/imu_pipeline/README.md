# imu_pipeline

使用 tf 将 sensor_msgs/Imu 消息转换为新的坐标框架。

## 项目链接

- GitHub: <https://github.com/ros-perception/imu_pipeline>

## 项目介绍
imu_pipeline是一个ROS元包，用于处理和预处理IMU相关消息，为后续订阅者提供更易用的IMU数据。它包含imu_transformer和imu_processors两个核心模块，支持ROS 2 Humble至Jazzy等多个ROS 2版本，可通过tf/tf2工具将sensor_msgs/Imu、sensor_msgs/MagneticField等消息转换到新的坐标系中。

## 主要特性
1. 坐标系转换：通过tf2实现IMU、磁场数据的坐标系转换，适配不同的传感器数据使用需求
2. IMU预处理工具：提供imu_integrator（简易平面IMU积分工具）、imu_bias_remover（基于/cmd_vel或/odom重新校准IMU偏置）等预处理功能
3. 多ROS版本支持：包含ros2主分支（适配ROS 2 Kilted及后续版本）、jazzy分支（适配ROS 2 Humble至Jazzy），兼容性广泛
