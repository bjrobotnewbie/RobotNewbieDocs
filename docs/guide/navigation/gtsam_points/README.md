# gtsam_points
- GitHub仓库: https://github.com/koide3/gtsam_points

## 项目概述
gtsam_points是一个基于GTSAM的因素图和优化器集合，专门用于基于距离传感器的SLAM（同时定位与地图构建）。该库提供了多种点云匹配算法的实现，包括点到点、点到平面ICP、广义ICP、体素化广义ICP（VGICP）及其GPU加速版本，还有基于点到平面和点到边距离组合的LOAM因子等，适用于机器人导航和三维建图领域的研究和开发。