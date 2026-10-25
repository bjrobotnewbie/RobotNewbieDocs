# TWIST2

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/data-collection/TWIST2/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[arXiv 2025] TWIST2：可扩展、便携且全面的机器人数据采集系统

## 项目链接

- GitHub: <https://github.com/amazon-far/TWIST2>
- 项目主页: <https://yanjieze.com/TWIST2>

## 项目介绍
TWIST2是2025年arXiv发布的可扩展、便携且全面的人形机器人数据采集系统，支持通过PICO VR头显控制Unitree G1机器人，可在仿真环境与真实硬件中实现有线连接的遥操作，用于人形机器人数据采集与相关研究。目前项目已开源，核心代码可实现控制器训练、部署、遥操作数据采集及在线运动重定向等功能，相关高级策略学习部分将基于iDP3框架单独发布。

## 主要特性
1. 支持双Conda环境配置，适配不同依赖需求（`twist2`环境用于控制器训练、部署与数据采集，`gmr`环境用于在线运动重定向）
2. 兼容仿真与真实硬件场景，可通过PICO VR头显实现Unitree G1机器人的有线遥操作
3. 集成ROS、SLAM、RL相关技术，支持运动重定向、ONNX模型推理、语音控制等功能
4. 提供完整的依赖安装流程，包含Isaac Gym、rsl_rl、legged_gym等核心依赖的配置步骤
