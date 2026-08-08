# phobos

Blender的一个插件，支持在所见即所得环境中创建URDF、SDF和SMURF机器人模型。

## 项目链接

- GitHub: <https://github.com/dfki-ric/phobos>

## 项目概述

## 项目介绍
Phobos是一款面向Blender 3.3LTS的插件，同时也可作为Python命令行工具使用，用于机器人模型的创建与编辑。它支持所见即所得（WYSIWYG）的机器人模型制作，可导出URDF、SDF、SMURF格式模型，以及STL、OBJ、DAE等通用网格格式，生成的模型可用于ROS、ROCK等机器人框架，以及MARS、Gazebo等实时仿真环境。该项目由德国不来梅DFKI机器人创新中心与不来梅大学机器人团队开发。

## 主要特性
1.  支持Blender可视化编辑机器人模型，可导出多种主流机器人模型格式与网格格式
2.  同时提供命令行工具与Blender插件两种使用方式
3.  支持模型版本升级迁移，适配新版Blender着色器要求
4.  支持配置继承，可灵活调整项目配置，2.1.0版本重构了CI使用流程并优化了可配置性
