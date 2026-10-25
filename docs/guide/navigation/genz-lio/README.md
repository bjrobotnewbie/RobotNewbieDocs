# genz-lio

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/genz-lio/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

GenZ-LIO：最先进的鲁棒 LiDAR-惯性里程计（IEEE T-FR 2026）

## 项目链接

- GitHub: <https://github.com/cocel-postech/genz-lio>

## 项目介绍
GenZ-LIO是一款SOTA级鲁棒LiDAR-inertial odometry方案，发表于IEEE T-FR 2026，核心功能是在封闭空间、开放环境及两者过渡场景下实现高效、高精度的LiDAR惯性里程计算法，支持处理录制数据，无需ROS环境即可运行。

## 主要特性
1. 适配多场景：覆盖封闭空间、开放环境及场景过渡场景
2. 多语言与平台支持：提供C++核心实现，支持Python 3.8-3.12，兼容ROS 1 Noetic、ROS 2 Humble/Jazzy
3. 便捷部署：支持pip安装，预编译C++扩展，无需本地编译或ROS安装，提供核心CLI及可选的可视化工具
4. 实验支持：提供论文基准实验的序列配置文件，以及自定义传感器录制的模板配置文件
