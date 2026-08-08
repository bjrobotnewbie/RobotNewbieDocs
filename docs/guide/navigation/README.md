# 机器人导航

机器人导航是指机器人在环境中自主移动并完成任务的技术，是移动机器人的核心能力之一。本章节涵盖 SLAM（同时定位与建图）、定位、导航栈、建图等核心技术。

## 导航技术分类说明

| 分类 | 主要内容 | 典型项目 |
|------|---------|---------|
| **SLAM 教材与学习** | SLAM 理论教材与课程代码 | SLAM Handbook, 视觉SLAM十四讲, slam_lecture_codes |
| **视觉 SLAM** | 基于相机的 SLAM 系统 | pySLAM, SuperVINS, VGGT-SLAM, RTAB-Map |
| **激光 SLAM 与里程计** | 基于激光雷达的里程计与建图 | KISS-ICP, GLIM, mola, lidar_slam_ros2 |
| **ROS SLAM 与导航栈** | 集成 ROS 的 SLAM 与导航 | hector_slam, slam_toolbox, dddmr_navigation |
| **定位与组合导航** | 多传感器融合定位 | MINS, KF-GINS |

> **注意**：视觉语言导航 (VLN) 模型已归类到 [基础模型](/guide/embodied-models/vln/README) 目录下。通用优化库 g2o、GTSAM 已归类到 [数学基础/优化理论](/guide/math/optimization-theory/README)。

## 项目列表

### SLAM 教材与学习资源

- [SLAM 手册](/guide/navigation/slam-handbook/README) - 剑桥大学出版社《SLAM手册》，系统覆盖SLAM理论与应用
- [视觉SLAM十四讲](/guide/navigation/slambook2/README) - 从理论到实践的视觉SLAM系统教材及配套代码
- [SLAM课程代码](/guide/navigation/slam_lecture_codes/README) - 涵盖数学基础到完整SLAM系统的教程代码
- [slamplay](/guide/navigation/slamplay/README) - 集成 g2o/gtsam/ceres/OpenCV/PCL 的 SLAM 工具启动集

### 视觉 SLAM

- [pySLAM](/guide/navigation/pyslam/README) - 混合 Python/C++ 视觉SLAM管道，支持单目/立体/RGB-D
- [SuperVINS](/guide/navigation/SuperVINS/README) - 集成 SuperPoint+LightGlue 的视觉惯性SLAM框架
- [VGGT-SLAM](/guide/navigation/VGGT-SLAM/README) - 基于 SL(4) 流形优化的稠密RGB SLAM
- [VSLAM-LAB](/guide/navigation/VSLAM-LAB/README) - 视觉SLAM系统编译配置与评估框架
- [RTAB-Map](/guide/navigation/rtabmap/README) - 实时SLAM库，支持多种传感器和ROS集成

### 激光 SLAM 与里程计

- [KISS-ICP](/guide/navigation/kiss-icp/README) - 开箱即用的激光雷达里程计，几乎无需调参
- [GLIM](/guide/navigation/glim/README) - 基于点云的3D定位与建图框架，支持GPU加速
- [lidar_slam_ros2](/guide/navigation/lidar_slam_ros2/README) - ROS2 激光SLAM建图，输出Autoware-ready地图
- [lidar_localization_ros2](/guide/navigation/lidar_localization_ros2/README) - ROS2 激光雷达运行时定位与重定位
- [mola](/guide/navigation/mola/README) - 模块化定位与SLAM框架，支持激光里程计和LIO
- [mola_lidar_odometry](/guide/navigation/mola_lidar_odometry/README) - 基于 MOLA/MRPT 的激光里程计组件
- [gtsam_points](/guide/navigation/gtsam_points/README) - 基于 GTSAM 的点云匹配因子，用于距离传感器SLAM
- [KISS-Matcher](/guide/navigation/KISS-Matcher/README) - 快速鲁棒的点云配准工具，含ROS2 SLAM示例

### 点云匹配与建图工具

- [mp2p_icp](/guide/navigation/mp2p_icp/README) - 多原素ICP算法库，MOLA SLAM组件
- [map-anything](/guide/navigation/map-anything/README) - Meta AI 通用前馈式度量三维重建框架

### ROS SLAM 与导航栈

- [hector_slam](/guide/navigation/hector_slam/README) - 用于开放环境的ROS SLAM软件包
- [slam_toolbox](/guide/navigation/slam_toolbox/README) - ROS2 2D SLAM工具集，支持终身建图
- [dddmr_navigation](/guide/navigation/dddmr_navigation/README) - 移动机器人3D导航软件栈，集成SLAM+YOLO+路径规划
- [pb2025_sentry_nav](/guide/navigation/pb2025_sentry_nav/README) - RoboMaster哨兵导航套件，基于NAV2框架

### 定位与组合导航

- [MINS](/guide/navigation/MINS/README) - 多传感器紧耦合惯性导航系统，融合IMU/轮速/相机/GNSS/LiDAR
- [KF-GINS](/guide/navigation/KF-GINS/README) - 基于EKF的GNSS/INS组合导航系统

### 导航应用与建图工具

- [rtabmap_drone_example](/guide/navigation/rtabmap_drone_example/README) - 基于RTAB-Map的无人机2D自主导航示例
- [spatio_temporal_voxel_layer](/guide/navigation/spatio_temporal_voxel_layer/README) - 基于OpenVDB的3D体素环境表示，替代ROS导航栈voxel_grid
- [DotRecast](/guide/navigation/DotRecast/README) - Recast & Detour 导航网格工具集C#移植版
- [vortex-auv](/guide/navigation/vortex-auv/README) - 无人水下航行器(AUV)引导、导航与控制软件栈
- [All-3R-SLAM-in-this-Repo](/guide/navigation/All-3R-SLAM-in-this-Repo/README) - 3D几何基础模型(DUSt3R/MASt3R)与SLAM应用资源汇总
- [mrpt（:zap: 移动机器人编程工具包（MRP…）](/guide/navigation/mrpt/README)
- [awesome-NeRF-and-3DGS-SLAM（SLAM/机器人领域内隐式表示、NeRF…）](/guide/navigation/awesome-NeRF-and-3DGS-SLAM/README)
- [visual-slam-roadmap（2026年成为Visual-SLAM开发…）](/guide/navigation/visual-slam-roadmap/README)
- [OpenCPN（一款简洁的海图绘制器/导航仪。这是一款跨…）](/guide/navigation/OpenCPN/README)
- [mesh_navigation（Mesh Navigation Stac…）](/guide/navigation/mesh_navigation/README)
- [Ultra-Fusion（Ultra-Fusion：传感器退化与时…）](/guide/navigation/Ultra-Fusion/README)
- [SpiceyPy（SpiceyPy：SPICE工具包的Py…）](/guide/navigation/SpiceyPy/README)
- [XCSoar（……开源滑翔伞飞行电脑）](/guide/navigation/XCSoar/README)
- [kalman_filter_localization_ros2（基于卡尔曼滤波的gnss/imu定位）](/guide/navigation/kalman_filter_localization_ros2/README)
- [routingpy（🌎 这是一个 Python 库，用于以统…）](/guide/navigation/routingpy/README)
- [DynOSAM（DynoSAM：动态物体平滑建图 官方代…）](/guide/navigation/DynOSAM/README)
- [pure-maps（地图与导航）](/guide/navigation/pure-maps/README)
- [Awesome-Transformer-based-SLAM（基于Transformer的SLAM论文…）](/guide/navigation/Awesome-Transformer-based-SLAM/README)
- [UMI-3D（UMI-3D SLAM与数据处理流水线：…）](/guide/navigation/UMI-3D/README)
- [fast_LIMO（一个紧耦合实时激光雷达-惯性SLAM算法…）](/guide/navigation/fast_LIMO/README)
- [mrpt_navigation（封装了MRPT核心功能的ROS 2节点，…）](/guide/navigation/mrpt_navigation/README)
- [SuperSLAM（SuperSLAM：基于深度学习的视觉S…）](/guide/navigation/SuperSLAM/README)
- [GroundSLAM（GroundSLAM：一种利用地面纹理的…）](/guide/navigation/GroundSLAM/README)
- [evo（用于里程计与SLAM评估的Python包）](/guide/navigation/evo/README)
- [isaac_ros_visual_slam（基于NVIDIA加速cuVSLAM的视觉…）](/guide/navigation/isaac_ros_visual_slam/README)
- [NeuPAN（[TRO 2025] NeuPAN: 基…）](/guide/navigation/NeuPAN/README)
- [genz-icp（GenZ-ICP：SOTA 鲁棒激光雷达…）](/guide/navigation/genz-icp/README)
- [rko_lio（无需传感器特定建模的稳健激光雷达-惯性里…）](/guide/navigation/rko_lio/README)
- [Ground-Fusion（Ground-Fusion：一个对边缘场…）](/guide/navigation/Ground-Fusion/README)
- [li_slam_ros2（紧耦合激光雷达惯性NDT/GICP SL…）](/guide/navigation/li_slam_ros2/README)
- [rmcl（基于3D三角网格与几何场景图的移动机器人…）](/guide/navigation/rmcl/README)
- [VLX-Go（VLX-Go：开放世界具身AI导航）](/guide/navigation/VLX-Go/README)
- [organicmaps（🍃 Organic Maps 是一款面向…）](/guide/navigation/organicmaps/README)
- [autoware_universe](/guide/navigation/autoware_universe/README)
- [mapbox-navigation-ios（基于iOS Swift实现的逐向导航逻辑…）](/guide/navigation/mapbox-navigation-ios/README)
- [navit（一款适用于多种操作系统的开源（GPL v…）](/guide/navigation/navit/README)
- [awesome-visual-localization（一份精心整理的优秀视觉定位研究工作列表）](/guide/navigation/awesome-visual-localization/README)
- [LIO-SAM_based_relocalization（本系统开发了一个可基于构建地图重新定位机…）](/guide/navigation/LIO-SAM_based_relocalization/README)
- [Structure-PLP-SLAM（[ICRA'23] 结构 PLP-SLA…）](/guide/navigation/Structure-PLP-SLAM/README)
- [mapbox-java（Mapbox Java SDK – Ja…）](/guide/navigation/mapbox-java/README)
- [navigation2_tutorials（https://docs.nav2.or…）](/guide/navigation/navigation2_tutorials/README)
- [beluga（C++17 实现的通用蒙特卡洛局部化（M…）](/guide/navigation/beluga/README)
- [mick_robot（基于 ROS2 的移动机器人导航开源项目）](/guide/navigation/mick_robot/README)
- [MegaLoc（任意定位任务中的图像检索模型）](/guide/navigation/MegaLoc/README)
- [SAGE-3D_Official（这是论文"Towards Physica…）](/guide/navigation/SAGE-3D_Official/README)
- [vtr3（VT&R3 是 Teach and Re…）](/guide/navigation/vtr3/README)
- [ORB-SLAM3-ROS2-Docker（该仓库包含运行 ROS2 Humble …）](/guide/navigation/ORB-SLAM3-ROS2-Docker/README)
- [mrpt_slam（MRPT 中的 SLAM 算法 ROS …）](/guide/navigation/mrpt_slam/README)
- [Kimera-VIO（具有 SLAM 能力的视觉惯性里程计与三…）](/guide/navigation/Kimera-VIO/README)
- [OrienterNet（论文"OrienterNet 在带有神经…）](/guide/navigation/OrienterNet/README)
- [awesome-robot-social-navigation（机器人社交导航精选列表）](/guide/navigation/awesome-robot-social-navigation/README)
- [full_linear_wheel_odometry_factor（全线性轮式 odometry 因子为轮式…）](/guide/navigation/full_linear_wheel_odometry_factor/README)
## 与其他分类的区别

| 目录 | 定位 | 主要特点 |
|------|------|---------|
| **navigation/** | 传统导航技术栈 | SLAM、定位、建图、导航栈 |
| **embodied-models/vln/** | AI 导航模型 | 端到端、多模态融合、语言驱动的导航 |
| **planning/path-planning/** | 路径规划算法 | A*, RRT*, Dijkstra 等几何寻路算法 |
| **math/optimization-theory/** | 优化数学库 | g2o、GTSAM 等通用图优化/因子图优化库 |
