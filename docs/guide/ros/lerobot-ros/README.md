# lerobot-ros

基于 LeRobot 的 ROS 机器人手臂轻量级控制接口

## 项目链接

- GitHub: <https://github.com/ycheng517/lerobot-ros>

## 项目概述

## 项目介绍
lerobot-ros是一个通用ROS 2接口仓库，作为轻量级封装工具，可以将兼容ros2_control或MoveIt的机械臂连接到LeRobot生态系统中。同时提供了用于6自由度末端执行器控制的游戏手柄遥操作，以及关节位置控制的键盘遥操作工具。

## 主要特性
1.  支持多种控制模式：
    - 基于ros2_control的关节位置控制，支持joint_trajectory_controller和position_controllers
    - 基于MoveIt 2的末端执行器速度控制，使用MoveIt Servo实现
    - 基于ros2_control的夹爪控制，支持joint_trajectory_controller和Gripper Action Controller
2.  仅在ROS 2 Jazzy版本测试通过，依赖ros2_control，如需末端控制还需安装MoveIt2
3.  提供了完整的快速上手流程，可实现模拟SO-101机械臂的键盘遥操作。
