# spatio_temporal_voxel_layer
- GitHub仓库: https://github.com/SteveMacenski/spatio_temporal_voxel_layer
- 项目主页: http://wiki.ros.org/spatio_temporal_voxel_layer

## 项目概述
这是一个用于替代voxel_grid的环境体素表示工具，基于OpenVDB库开发，能够高效维护三维体素表示的世界空间。该项目改进了原有的voxel grid包，扩展了用户可用的功能，适用于ROS导航栈，可以与多个深度相机或激光雷达配合使用，显著降低了全局代价图更新的CPU占用率，适用于移动机器人的导航环境感知和建图任务。