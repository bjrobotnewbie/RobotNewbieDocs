# vscode_ros2_workspace

一个将VSCode用作ROS2开发IDE的模板。

## 项目链接

- GitHub: <https://github.com/althack/vscode_ros2_workspace>
- 项目主页: https://althack.github.io/vscode_ros2_workspace/

## 项目概述

## 项目介绍
本项目是一个VSCode ROS2开发工作区模板，用于将VSCode作为IDE进行ROS2开发，支持通过Docker容器快速搭建开发环境，适配NVIDIA GPU加速场景。用户可通过GitHub模板一键创建专属ROS2开发仓库，默认基于`osrf/ros:jazzy-desktop-full`镜像，也可自行修改Dockerfile适配其他ROS版本。

## 主要特性
1.  **代码格式化**：内置ROS2官方认可的格式化工具，C++使用ament_uncrustify配置的uncrustify，Python使用符合ROS2风格指南的autopep8
2.  **预定义任务**：提供丰富的可自定义开发任务，可直接在VSCode中调用
3.  **多语言调试**：支持Python代码调试、C++的gdb调试以及ROS launch文件调试
4.  **CI集成**：内置基础持续集成配置，支持cppcheck、cpplint、uncrustify等多种代码检查工具，可灵活删减检查项
