# aruco_ekf_slam

基于 ArUco 的 EKF-SLAM

## 项目链接

- GitHub: <https://github.com/ydsf16/aruco_ekf_slam>
- 项目主页: <https://zhuanlan.zhihu.com/p/45207081>

## 项目介绍
aruco_ekf_slam是基于ArUco标记的扩展卡尔曼滤波同时定位与建图（EKF-SLAM）项目，适用于ROS平台，依赖Opencv 3.1、Eigen库，可通过ArUco标记辅助实现机器人的定位与环境建图，提供了演示数据集与操作指引，遵循GPLv3开源协议，商业用途可联系作者。

## 主要特性
- 基于ArUco标记实现EKF-SLAM算法，适配ROS环境
- 提供完整的演示流程：代码编译、启动SLAM节点、播放对应数据集的rosbag即可运行
- 配套有专用演示数据集，降低测试门槛
- 开源协议清晰，支持非商业场景自由使用
