# ROS 机器人操作系统

ROS (Robot Operating System) 是机器人领域最常用的开源操作系统，提供了硬件抽象、设备驱动、库函数、可视化、消息传递和软件包管理等一系列功能，极大地简化了复杂机器人系统的开发。

## ROS 核心与文档

- [ROS 1](/guide/ros/ros1/README) - 传统机器人操作系统
- [ROS 2](/guide/ros/ros2/README) - 新一代机器人操作系统
- [ROS 2 官方文档](/guide/ros/ros2_documentation/README) - ros2_documentation
- [ROS 教程](/guide/ros/ros-tutorials/README) - 官方全套教程
- [common_interfaces](/guide/ros/common_interfaces/README) - ROS 2 标准消息定义
- [rclcpp](/guide/ros/rclcpp/README) - ROS 2 C++ 客户端库
- [rclpy](/guide/ros/rclpy/README) - ROS 2 Python 客户端库
- [rclnodejs](/guide/ros/rclnodejs/README) - ROS 2 Node.js 客户端库
- [ros2_rust](/guide/ros/ros2_rust/README) - ROS 2 Rust 绑定
- [roslibjs](/guide/ros/roslibjs/README) - ROS JavaScript 库
- [rosdistro](/guide/ros/rosdistro/README) - ROS 发行版仓库管理
- [demos](/guide/ros/demos/README) - ROS 2 官方示例

## ROS 工具

- [RViz](/guide/ros/rviz/README) - 3D 可视化工具
- [ros2-performance](/guide/ros/ros2-performance/README) - ROS 2 性能测试框架
- [robo-boy](/guide/ros/robo-boy/README) - ROS 2 Web 控制应用
- [ros-mcp-server](/guide/ros/ros-mcp-server/README) - LLM 与 ROS 桥接工具

## ROS 控制框架

- [ros2_control_demos](/guide/ros/ros2_control_demos/README) - 控制框架示例
- [ros2_controllers](/guide/ros/ros2_controllers/README) - ROS 2 标准控制器集
- [gz_ros2_control](/guide/ros/gz_ros2_control/README) - Gazebo-ros2_control 桥接

## ROS 感知包

- [image_pipeline](/guide/ros/image_pipeline/README) - ROS 2 图像处理管道
- [perception_pcl](/guide/ros/perception_pcl/README) - PCL ROS 接口栈
- [realsense-ros](/guide/ros/realsense-ros/README) - Intel RealSense ROS 驱动
- [zed-ros2-wrapper](/guide/ros/zed-ros2-wrapper/README) - ZED 深度相机 ROS 2 封装

## ROS 导航与规划

- [Navigation2](/guide/ros/navigation2/README) - ROS 2 导航栈
- [rtabmap_ros](/guide/ros/rtabmap_ros/README) - RTAB-Map SLAM ROS 包

## ROS 机器人驱动

- [spot_ros2](/guide/ros/spot_ros2/README) - Boston Dynamics Spot ROS 2 驱动
- [stretch_ros2](/guide/ros/stretch_ros2/README) - Hello Robot Stretch ROS 2
- [unitree_ros](/guide/ros/unitree_ros/README) - 宇树机器人 ROS 仿真包
- [crane_x7_ros](/guide/ros/crane_x7_ros/README) - CRANE-X7 机械臂 ROS 包
- [franka_ros2](/guide/ros/franka_ros2/README) - Franka 机械臂 ROS 2 集成
- [Universal_Robots_ROS2_Description](/guide/ros/Universal_Robots_ROS2_Description/README) - UR 机械臂 URDF
- [Universal_Robots_ROS2_Driver](/guide/ros/Universal_Robots_ROS2_Driver/README) - UR 机械臂 ROS 2 驱动
- [g1pilot](/guide/ros/g1pilot/README) - Unitree G1 人形机器人 ROS 2
- [open_manipulator](/guide/ros/open_manipulator/README) - OpenMANIPULATOR ROS 2

## ROS 应用框架

- [aerostack2](/guide/ros/aerostack2/README) - ROS 2 无人机自主框架
- [carma-platform](/guide/ros/carma-platform/README) - 合作式自动驾驶 ROS 平台
- [fusioncore](/guide/ros/fusioncore/README) - ROS 2 UKF 传感器融合 SDK
- [mavros](/guide/ros/mavros/README) - MAVLink-ROS 通信网关

## 其他机器人中间件

- [Orocos](/guide/ros/orocos/README) - 开放式机器人控制软件
- [PyRobot](/guide/ros/pyrobot/README) - Python 机器人控制库
- [Zenoh](/guide/ros/zenoh/README) - 轻量级消息中间件
- [YARP](/guide/ros/yarp/README) - Yet Another Robot Platform

## 分类说明

| 分类 | 主要内容 | 应用场景 |
|------|---------|---------|
| **ROS 核心** | ROS 1/2 本体、客户端库、文档 | ROS 系统开发基础 |
| **ROS 工具** | 可视化、性能测试、Web 控制 | ROS 开发与调试 |
| **ROS 控制框架** | ros2_control 生态 | 机器人控制器开发 |
| **ROS 感知包** | 图像、点云、传感器驱动 | 传感器数据处理 |
| **ROS 导航与规划** | Nav2、MoveIt 2、SLAM | 自主导航与操作 |
| **ROS 机器人驱动** | 各品牌机器人 ROS 包 | 特定机器人开发 |
| **ROS 应用框架** | 无人机、自动驾驶、传感器融合 | 应用层开发 |
| **其他中间件** | Orocos、YARP、Zenoh 等 | ROS 替代方案 |

- [dora（DORA（面向数据流的机器人架构，Dat…）](/guide/ros/dora/README)

- [Fast-DDS（最完整的DDS——久经考验：拥有大量成功…）](/guide/ros/Fast-DDS/README)

- [ros-robotics-companies（一份使用机器人操作系统（ROS和ROS …）](/guide/ros/ros-robotics-companies/README)

- [copper-rs（Copper是一个面向机器人的操作系统—…）](/guide/ros/copper-rs/README)

- [rosbridge_suite（rosbridge v2 协议的服务端实…）](/guide/ros/rosbridge_suite/README)

- [yolo_ros（适用于 ROS 2 的 Ultralyt…）](/guide/ros/yolo_ros/README)

- [go2_ros2_sdk（宇树Unitree GO2 AIR/PR…）](/guide/ros/go2_ros2_sdk/README)

- [ros_tutorials（ROS wiki 上教程所用的代码）](/guide/ros/ros_tutorials/README)

- [urdf-loaders（适用于Unity和THREE.js的UR…）](/guide/ros/urdf-loaders/README)

- [rslidar_sdk（面向ROS与ROS2的镭神智能LiDAR…）](/guide/ros/rslidar_sdk/README)

- [open_mower_ros](/guide/ros/open_mower_ros/README)

- [ros-bridge（用于CARLA模拟器的ROS桥接）](/guide/ros/ros-bridge/README)

- [rmw_zenoh（基于Zenoh作为中间件实现的ROS 2…）](/guide/ros/rmw_zenoh/README)

- [RoboticsAcademy（通过JdeRobot学习机器人技术）](/guide/ros/RoboticsAcademy/README)

- [rosbag2](/guide/ros/rosbag2/README)

- [ros2ai（ros2ai 是基于大语言模型驱动的下一…）](/guide/ros/ros2ai/README)

- [zenoh-plugin-ros2dds（适用于ROS2、基于DDS RMW的Ze…）](/guide/ros/zenoh-plugin-ros2dds/README)

- [easy_handeye2（面向ROS2的自动化、硬件无关手眼标定）](/guide/ros/easy_handeye2/README)

- [ros2cli（ROS 2 命令行界面工具）](/guide/ros/ros2cli/README)

- [ros2_medkit（ros2_medkit - 用于ROS …）](/guide/ros/ros2_medkit/README)

- [mujoco_ros2_control（为 MuJoCo 物理模拟器提供了一个 …）](/guide/ros/mujoco_ros2_control/README)

- [zenoh-plugin-dds（一个支持透明路由DDS数据的zenoh插…）](/guide/ros/zenoh-plugin-dds/README)

- [rmw_fastrtps（基于eProsima Fast RTPS…）](/guide/ros/rmw_fastrtps/README)

- [image_common（ROS中处理图像的通用代码）](/guide/ros/image_common/README)

- [rosys（一个基于Web技术的全Python机器人…）](/guide/ros/rosys/README)

- [kachaka-api（智能家具平台「Kachaka」API）](/guide/ros/kachaka-api/README)

- [vlink（VLink is a high-perf…）](/guide/ros/vlink/README)

- [PlotJuggler（你值得拥有的时间序列可视化工具。）](/guide/ros/PlotJuggler/README)

- [imu_tools（适用于IMU设备的ROS工具）](/guide/ros/imu_tools/README)

- [vscode_ros2_workspace（一个将VSCode用作ROS2开发IDE…）](/guide/ros/vscode_ros2_workspace/README)

- [examples（适用于ROS 2的示例软件包）](/guide/ros/examples/README)

- [unitree_ros2](/guide/ros/unitree_ros2/README)

- [docker-ros2-desktop-vnc（🐳 该仓库提供可通过HTML5 VNC界…）](/guide/ros/docker-ros2-desktop-vnc/README)

- [ros2-depth-anything-v3-trt（基于Depth Anything V3、…）](/guide/ros/ros2-depth-anything-v3-trt/README)

- [SMACC2（适用于C++编写的ROS2（机器人操作系…）](/guide/ros/SMACC2/README)

- [Mobile_Robot_URDF_Maker（这是一个可帮助你借助其向导在数分钟内轻松…）](/guide/ros/Mobile_Robot_URDF_Maker/README)

- [wato_monorepo（适用于WATonomous自动驾驶软件流…）](/guide/ros/wato_monorepo/README)

- [isaac_ros_manipulation（机械臂操纵工作流）](/guide/ros/isaac_ros_manipulation/README)

- [livox_ros_driver2（Livox 设备驱动支持 ROS（兼容 …）](/guide/ros/livox_ros_driver2/README)

- [ros-noetic（Vinca 配置文件（适用于 ROS N…）](/guide/ros/ros-noetic/README)

- [OrbbecSDK_ROS2（OrbbecSDK ROS2 封装）](/guide/ros/OrbbecSDK_ROS2/README)

- [better_launch（ROS2 启动系统的更好替代品：直观、简…）](/guide/ros/better_launch/README)

- [ros2_tracing（ROS 2 追踪工具）](/guide/ros/ros2_tracing/README)

- [ros2_robotiq_gripper](/guide/ros/ros2_robotiq_gripper/README)

- [point_cloud_transport（点云压缩：ROS）](/guide/ros/point_cloud_transport/README)

- [robot_localization（robot_localization 是…）](/guide/ros/robot_localization/README)

- [universal_robot（ROS-工业级通用机器人支持 (http…）](/guide/ros/universal_robot/README)

- [Universal_Robots_ROS_Driver（支持 CB3 和 e 系列机器人的 Un…）](/guide/ros/Universal_Robots_ROS_Driver/README)

- [ros2_cookbook（ROS2 代码片段）](/guide/ros/ros2_cookbook/README)

- [robot_calibration（机器人通用标定）](/guide/ros/robot_calibration/README)

- [OrbbecSDK_ROS1（Orbbec SDK ROS 封装）](/guide/ros/OrbbecSDK_ROS1/README)

- [Dalaran（达拉兰 —— Apache 2.0 许可…）](/guide/ros/Dalaran/README)

- [webots_ros2（Webots ROS 2 包）](/guide/ros/webots_ros2/README)

- [xarm_ros2（UFACTORY 机器人产品 ROS2 …）](/guide/ros/xarm_ros2/README)

- [lerobot-ros（基于 LeRobot 的 ROS 机器人…）](/guide/ros/lerobot-ros/README)

- [ros2_unbag（一个 ROS 2 工具，用于将 bag …）](/guide/ros/ros2_unbag/README)

- [px4-ros2-interface-lib（使用 ROS 2 通过计算机伙伴与 PX…）](/guide/ros/px4-ros2-interface-lib/README)

- [ros2（机器人操作系统（ROS）是一个用于机器人…）](/guide/ros/ros2/README)

- [rviz（ROS 3D 机器人视觉器）](/guide/ros/rviz/README)
