# RC_WheelLeg

关键词：ROBOCON、四足机器人、仿生足式、强化学习、RL、Mjlab、Mujoco、Odin1、sim2sim、sim2real。

## 项目链接

- GitHub: <https://github.com/zeitvex/RC_WheelLeg>

## 项目介绍
本项目是山东华宇工学院HYNova战队的开源轮足机器人项目，核心为16DOF串联轮足机器人，用于ROBOCON仿生足式障碍赛，曾获全国一等奖（第7名，前5%）。项目沿8DOF基础版本→16DOF升级版本迭代，已完整开源机械、硬件、固件、软件、BOM、装配、训练、部署及比赛代码，为备赛ROBOCON的队伍提供参考。

## 主要特性
1. 采用4条轮腿构型，每条腿含3个关节和1个驱动轮，共16个RS02执行器，适配Jetson Orin Nano 8G平台
2. 基于RL算法，结合MuJoCo仿真、Mjlab训练工具，通过Sim2Sim验证、Py与ROS 2/C++双线实现Sim2Real真机部署
3. 开源内容覆盖SolidWorks机械源文件、仿真模型、训练任务、多版本Sim2Real部署栈及导航工具链，支持算法迭代与真机调试
