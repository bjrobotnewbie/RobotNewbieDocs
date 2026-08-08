# lidar_slam_ros2
- GitHub仓库: https://github.com/rsasaki0109/lidar_slam_ros2
- 项目主页: https://rsasaki0109.github.io/lidar_slam_ros2/

## 项目概述
lidar_slam_ros2是一个ROS 2点云地图SLAM包，能够将rosbag数据转换为可用于自动驾驶的地图，输出Autoware-ready的点云地图、地图投影信息和自动生成的Lanelet2地图。该项目的前端采用RKO-LIO算法，后端采用基于图的SLAM，默认工作流程不包含GPL组件，适用于移动机器人的建图和导航任务，是机器人研究和开发的优秀工具。