# MPlib

MPlib 是一个轻量级 Python 运动规划库，脱离 ROS 依赖，便于在机器人操作任务中快速集成规划能力。

## 项目链接

- GitHub: <https://github.com/haosulab/MPlib>
- 项目主页: https://motion-planning-lib.readthedocs.io/

## 项目概述

MPlib 是一个面向机器人操作的轻量级运动规划 Python 包。它的设计目标是让用户无需搭建完整 ROS 环境，也能用少量 Python 代码完成常见机械臂运动规划功能，从而降低机器人仿真、研究和应用开发中的规划集成成本。

项目提供预编译 pip 包，支持 Ubuntu 20.04 及以上系统和 Python 3.8+。README 强调其安装简单、与 ROS 解耦，并配有教程和文档，适合在独立 Python 项目、仿真环境或学习型机器人项目中快速验证运动规划流程。

MPlib 适用于机械臂轨迹规划、避障规划、机器人操作算法实验和教学示例。对于不希望引入完整 ROS/MoveIt 工程栈的用户，它提供了一种更轻量、更容易脚本化的运动规划入口。