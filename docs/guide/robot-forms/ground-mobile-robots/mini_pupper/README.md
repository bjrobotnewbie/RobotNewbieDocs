# mini_pupper

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/robot-forms/ground-mobile-robots/mini_pupper/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

开源物理人工智能平台，连接 ROS 与 RL——从学习到变现。

## 项目链接

- GitHub: <https://github.com/mangdangroboticsclub/mini_pupper>

## 项目介绍
mini_pupper是一款开源实体AI平台，核心是搭载3-DoF无芯智能伺服关节，可实现从学习到落地应用的全流程支持，旨在为机器人相关开发提供实用的实体硬件载体，适配ROS、RL等技术栈，打通仿真与实体机器人的部署链路。

## 主要特性
1. 支持Sim2Real技术，可在高保真仿真环境中训练神经网络策略，直接部署到实体机器人，缩小仿真与现实的差距；
2. 原生兼容Better Actuator Models（BAM），精准捕捉关节摩擦物理特性，聚焦高级应用开发；
3. 原生支持micro-ROS，可在微控制器上实现可靠的实时执行器控制；
4. 适配ROS 2 Jazzy，提供开箱即用的SLAM建图、路径规划及自主导航（Nav2）模板；
5. 配套开源仓库包含RL物理引擎后端、BAM摩擦引擎、ROS 2核心栈、micro-ROS栈，覆盖从仿真到硬件控制的全链路开发需求。
