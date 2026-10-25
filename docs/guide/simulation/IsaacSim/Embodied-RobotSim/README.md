# Embodied-RobotSim

Embodied-RobotSim 是一个全面、基于 ROS 2 (Jazzy) 的移动机器人仿真工作区，配备 Franka FR3 机械臂、2D/D LiDAR、立体 RGB-D 相机以及一套丰富的先进传感器套件。该仿真集成了先进的算法，涵盖映射、导航、2D/3D 感知以及移动操作。

## 项目链接

- GitHub: <https://github.com/lyz678/Embodied-RobotSim>

## 项目介绍
Embodied-RobotSim 是基于 ROS 2 Jazzy、Isaac Sim 6.1 / Gazebo Harmonic 的移动抓取仿真工作空间，搭载带 Franka FR3 机械臂的移动机器人，集成 FAST-LIO、Nav2、YOLOE、语义 OctoMap、GraspNet/MoveIt、ACT 等先进算法，支持自然语言取物等具身任务。

## 主要特性
1. 多仿真环境支持：可通过 `--sim isaac|gazebo` 切换 Isaac Sim 或 Gazebo 仿真环境，支持建图、导航、抓取、具身任务等多种场景；
2. 自然语言交互：支持输入“到厨房拿可乐”等指令，可使用本地 Qwen 或云端 DashScope LLM 模型；
3. 多算法集成：融合 FAST-LIO 定位、Nav2 导航、语义 OctoMap 建图、GraspNet/MoveIt 或 ACT 抓取算法，支持 2D/3D 感知与移动操作；
4. 地图管理：支持持久语义地图（含物体、区域信息）与局部 OctoMap，支持地图交接与保存；
5. 灵活启动：提供 `start_embodied.sh`、`start_mapping_and_explore.sh`、`start_pick_and_place.sh` 等脚本快速启动不同任务，支持自定义参数配置。
