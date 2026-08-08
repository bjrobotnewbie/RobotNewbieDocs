# docker-ros2-desktop-vnc

🐳 该仓库提供可通过HTML5 VNC界面访问Ubuntu桌面与ROS 2环境的Dockerfile

## 项目链接

- GitHub: <https://github.com/Tiryoh/docker-ros2-desktop-vnc>
- 项目主页: https://memoteki.net/archives/2955

## 项目概述

## 项目介绍
本项目是一套Dockerfile集合，用于快速构建包含Ubuntu桌面环境与ROS 2的容器，并通过HTML5 VNC界面实现远程访问。用户无需在本地配置复杂的ROS 2开发环境，只需通过浏览器即可使用完整的ROS 2开发、测试环境。项目支持Humble、Iron、Jazzy、Lyrical、Rolling等多个ROS 2版本，镜像已自动发布至Docker Hub与GitHub Container Registry。

## 主要特性
1.  开箱即用：内置Ubuntu桌面与ROS 2完整环境，支持直接通过浏览器访问
2.  多版本兼容：覆盖主流ROS 2发行版，包含已停止维护的旧版本镜像
3.  便捷部署：仅需一条Docker运行命令即可启动容器，默认端口6080
4.  轻量化远程开发：无需本地安装ROS 2依赖，适合快速验证ROS 2功能、学习SLAM、RL等机器人开发技术
5.  持续集成：通过GitHub Actions自动构建并发布最新镜像
