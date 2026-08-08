# crisp_controllers

- 项目链接：https://github.com/learnsyslab/crisp_controllers
- 项目主页：https://learnsyslab.github.io/crisp_controllers/

## 项目概述
CRISP Controllers是一套基于ROS2的实时C++控制器集合，专为机械臂的柔顺力矩控制设计，兼容`ros2_control`框架。其核心特点包括：
1. 支持笛卡尔阻抗控制和操作空间控制等多种高级控制算法
2. 专为部署高层学习策略（如VLA、扩散模型等）和遥操作开发，适配现代机器人AI应用
3. 机器人无关设计，兼容任何提供力和扭矩接口的机械臂，具有高度通用性
4. 支持多个ROS2发行版，通过单个main分支进行维护，降低维护开销
5. 提供详细的文档、入门指南和演示示例，方便开发者快速上手

该项目可以帮助开发者快速在机械臂上部署基于学习的控制策略，实现灵活的机器人操作和遥操作任务。