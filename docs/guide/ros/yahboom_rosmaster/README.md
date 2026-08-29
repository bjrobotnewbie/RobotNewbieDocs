# yahboom_rosmaster

Yahboom 为 ROSMASTER X3 移动机器人提供的自动避障支持（ROS 2）

## 项目链接

- GitHub: <https://github.com/automaticaddison/yahboom_rosmaster>

## 项目介绍
本项目是面向Yahboom ROSMASTER X3麦克纳姆轮移动机器人的ROS 2自动适配支持包，适配Ubuntu系统与ROS 2 Lyrical版本。包含可在Gazebo仿真环境、RViz中可视化展示的机器人模型相关内容。

## 主要特性
1.  支持ROSMASTER X3麦克纳姆轮机器人的ROS 2快速适配
2.  提供Gazebo仿真与RViz可视化演示功能
3.  目前导航相关包`yahboom_rosmaster_navigation`和`yahboom_rosmaster_docking`可正常编译，但因ROS 2 Lyrical版本的`nav2_bringup`等包尚未提供Debian安装包，暂无法运行完整导航功能，其余代码均可正常使用。
