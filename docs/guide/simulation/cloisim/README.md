# cloisim

- 项目链接：https://github.com/lge-ros2/cloisim
- 项目主页：https://github.com/lge-ros2/cloisim/wiki

## 项目概述

CLOiSim 是一个基于 Unity 6 的高性能多机器人模拟器，可以直接从 SDFormat（SDF）描述文件动态构建仿真 3D 环境和机器人。支持通过 cloisim_ros 连接 ROS 2。

该项目开发目的是解决其他模拟器在加载带有复杂传感器套件的多个机器人时遇到的性能瓶颈。通过利用 Unity 高效的渲染和物理管线，CLOiSim 为大规模机器人仿真提供了可扩展的解决方案。

主要组件：
- **SDF 解析器**：使用 sdformat-sharp 作为 Unity 包，提供稳健全面的 SDF 1.6+ 规范解析
- **Unity 实现**：自动将 SDF 元素映射到 Unity 的 Visual、Collision 和 Physics (ArticulationBody) 组件
- **传输层**：通过 ZeroMQ (NetMQ) 实现高性能传感器数据和控制信号传输
- **Web 服务**：通过 Web 界面进行基于 JSON 的仿真控制和监控

支持 ROS 2 Humble 和 Jazzy，基于 MIT 许可证开源。
