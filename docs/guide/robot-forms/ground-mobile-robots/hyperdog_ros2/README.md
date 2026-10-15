# hyperdog_ros2

HyperDog 是一款完全基于 ROS 2 和 Micro-ROS 构建的四足机器人。

## 项目链接

- GitHub: <https://github.com/NDHANA94/hyperdog_ros2>

## 项目介绍
hyperdog_ros2是基于ROS 2与Micro-ROS开发的四足机器人HyperDog的ROS 2功能包集合，用于实现该四足机器人的运动控制与相关功能开发，配套有相关学术论文与演示视频。

## 主要特性
1. 包含三类核心ROS 2功能包：
   - hyperdog_msgs：定义机器人控制与坐标相关的消息接口，涵盖游戏手柄控制指令、各腿末端坐标及机体姿态参数；
   - hyperdog_teleop：提供游戏手柄控制节点，可将手柄指令转换为机器人控制命令；
   - hyperdog_ctrl：包含机体运动规划器与步态生成器，生成机体姿态与关节控制指令，实现机器人步态切换与运动控制。
2. 支持通过游戏手柄控制机器人，可切换步态类型、调整机体姿态与运动参数。
