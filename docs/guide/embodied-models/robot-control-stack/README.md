# Robot Control Stack
- GitHub仓库: https://github.com/RobotControlStack/robot-control-stack
- 项目主页: http://robotcontrolstack.org/

## 项目概述
Robot Control Stack（RCS）是一个轻量级、无需ROS的仿真到现实转换框架，专为现代机器人学习和视觉-语言-动作（VLA）模型设计。它基于Gymnasium封装，将MuJoCo仿真和真实机器人控制统一到一个无缝的API中，目前原生支持Franka FR3/Panda、xArm7、UR5e和SO101四款机器人。该框架解决了传统ROS/ROS2中间件在训练VLA模型和强化学习代理时的性能瓶颈，提供了高效的同步执行环境，便于研究人员快速训练和部署机器人智能体。