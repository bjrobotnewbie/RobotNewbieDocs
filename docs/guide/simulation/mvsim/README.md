# mvsim

- 项目链接：https://github.com/MRPT/mvsim
- 项目主页：https://mvsimulator.readthedocs.io/

## 项目概述

MVSim (MultiVehicle Simulator) 是一个轻量级、真实感的 2.5D 动力学模拟器，用于移动机器人和多智能体研究。它模拟轮式机器人和车辆，提供真实物理、传感器和多智能体支持。

设计目标是对于大规模实验足够快，同时对于动力学和传感器研究足够准确。

主要特点：
- 通过 XML 世界文件完全配置，大多数实验无需修改代码
- 可独立运行，可作为 ROS 2 节点，或嵌入到 C++/Python 应用程序
- 支持无头模式，用于 CI 流水线和 Docker 容器
- 支持多车辆世界，相互检测（机器人在 LiDAR 中可以看到彼此）
- 提供多种车辆动力学模型
- 支持多种传感器：轮式编码器、IMU、GPS、LiDAR、深度摄像头、碰撞检测器等
- 提供 BSD 3-Clause 开源许可证

该项目属于 MRPT 生态系统，文档完善，持续集成保证质量。
