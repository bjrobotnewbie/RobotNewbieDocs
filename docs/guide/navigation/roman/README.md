# roman

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/roman/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[RSS 2025] ROMAN: 一种视角无关的全局定位方法，通过匹配来自不同机器人视角的物体，即使在场景从相反视角观察时也能实现可靠的位姿估计。

## 项目链接

- GitHub: <https://github.com/mit-acl/roman>
- 项目主页: <http://acl.mit.edu/roman/>

## 项目介绍
ROMAN（Robust Object Map Alignment Anywhere）是RSS 2025收录的视角不变全局定位方法，核心为通过匹配不同机器人视角的开放集物体，结合物体几何、形状、语义信息实现位姿估计，支持机器人在场景处于相反视角时完成回环检测。项目包含开放集物体建图、物体地图配准及鲁棒数据关联算法代码，提供ROS1/2集成支持，依赖CLIPPER、Kimera-RPGO等工具，分为建图、数据关联、位姿图优化三个模块，对应Python子模块分别实现相关功能。

## 主要特性
1. 视角不变性：支持机器人在场景处于相反视角时仍能完成可靠的全局定位与回环检测
2. 开放集物体处理：基于RGB-D图像生成开放集物体地图，无需依赖预定义物体类别
3. 多模块架构：包含建图、数据关联、位姿图优化三个核心模块，可与VIO结合完成位姿优化
4. ROS兼容：提供独立的roman_ros仓库支持ROS1/2集成，便于机器人系统部署使用
