# robot_descriptions.py

可从主流Python机器人框架获取190余种机器人描述

## 项目链接

- GitHub: <https://github.com/robot-descriptions/robot_descriptions.py>

## 项目概述

## 项目介绍
这是一个Python机器人描述资源库，可以一键获取190+款主流开源机器人的模型描述文件。支持通过Python模块导入机器人描述，首次导入时会自动下载并缓存文件，覆盖绝大多数收录在Awesome Robot Descriptions中的机器人模型。所有模型均可成功在MuJoCo(MJCF格式)、Pinocchio、iDynTree、PyBullet和yourdfpy(URDF格式)等主流机器人仿真/计算框架中加载。

## 主要特性
1.  支持通过Conda或PyPI快速安装
2.  提供适配多款机器人框架的加载器，包括iDynTree、MuJoCo、Pinocchio、PyBullet、RoboMeshCat、yourdfpy
3.  自动下载并本地缓存机器人模型文件，无需手动管理资源
4.  兼容主流开源机器人生态，可直接在机器人开发、SLAM、RL等机器人研究场景中使用
