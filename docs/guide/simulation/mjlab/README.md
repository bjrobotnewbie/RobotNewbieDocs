# mjlab

- 项目链接：https://github.com/mujocolab/mjlab
- 项目主页：https://mujocolab.github.io/mjlab/

## 项目概述

mjlab 结合了 Isaac Lab 的基于管理器的 API 与 MuJoCo Warp（Google DeepMind MuJoCo 的 GPU 加速版本），为强化学习与机器人研究提供框架。

该框架提供了可组合的环境设计构建块，依赖最小，可直接访问原生 MuJoCo 数据结构。

主要特点：
- 需要 NVIDIA GPU 进行训练，macOS 仅支持评估
- 提供便捷的演示方式，可通过 uvx 直接运行演示，也支持 Google Colab
- 可通过 PyPI 安装，也支持源码编译和 Docker
- 提供夜间基准测试
- MIT 许可证开源

支持多种训练示例，包括 Unitree G1 人形机器人速度跟踪等。为基于 MuJoCo 的机器人强化学习研究提供了类似 Isaac Lab 的便捷 API。
