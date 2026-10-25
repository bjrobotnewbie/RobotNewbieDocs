# bobac-air-ground-delivery

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/applications/uav/bobac-air-ground-delivery/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 ROS 2 和 NVIDIA Isaac Sim 的机 - 地协同配送系统，支持机器人抓取与无人机视觉对齐。

## 项目链接

- GitHub: <https://github.com/Luky-hui/bobac-air-ground-delivery>

## 项目介绍
本项目是基于ROS 2与NVIDIA Isaac Sim开发的空地协同配送系统，集成了机械臂抓取、无人机视觉对齐功能，适用于机器人配送场景，支持ROS 2 Humble、Isaac Sim 4.5.0等技术栈，还结合了YOLOE视觉、cuRobo运动规划等工具，可在仿真环境中实现空地协同配送任务。

## 主要特性
1. 空地协同配送：整合地面机器人与无人机的作业能力，完成配送任务
2. 机械臂抓取：支持目标物体的抓取操作
3. 无人机视觉对齐：利用视觉技术实现无人机的精准定位与对齐
4. 仿真环境支持：基于NVIDIA Isaac Sim搭建仿真场景，可进行算法验证与测试
5. 多技术栈集成：兼容ROS 2、Python等技术，结合视觉识别、运动规划等工具实现完整功能
