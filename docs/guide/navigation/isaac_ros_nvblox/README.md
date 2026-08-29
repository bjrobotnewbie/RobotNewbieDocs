# isaac_ros_nvblox

基于 NVIDIA 加速的 3D 场景重建与 Nav2 局部代价地图提供者，使用 nvblox

## 项目链接

- GitHub: <https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_nvblox>
- 项目主页: <https://developer.nvidia.com/isaac-ros-gems>

## 项目介绍
Isaac ROS Nvblox是NVIDIA推出的ROS 2集成包，基于nvblox实现实时3D场景重建与导航局部代价地图生成。它可接收深度相机/3D LiDAR数据与位姿输入，通过GPU加速实时构建3D场景，并输出适配Nav2的2D局部代价地图，用于机器人导航避障，还支持将彩色3D重建结果通过RViz实时可视化。

## 主要特性
1.  基于GPU加速的实时3D场景重建，支持深度相机、3D LiDAR输入
2.  可生成适配Nav2的视觉避障局部代价地图
3.  支持三种运行模式：静态场景重建、带人体的动态场景重建、通用动态物体场景重建
4.  可通过UNet人体语义分割模型分离动态人物，优化动态场景下的建图效果
5.  基于底层独立C++库nvblox实现核心功能，兼容ROS 2生态
