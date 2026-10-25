# deep_grasp_demo

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/deep_grasp_demo/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

MoveIt 框架内的抓取检测深度学习方法

## 项目链接

- GitHub: <https://github.com/PickNikRobotics/deep_grasp_demo>
- 项目主页: <https://picknik.ai/>

## 项目介绍
本项目是基于深度学习的抓取检测演示仓库，可在MoveIt任务构造器中实现抓取位姿生成，适配Ubuntu 18.04 + ROS Melodic环境。项目包含三个功能包，分别集成不同的深度学习抓取方案，用于机械臂拾取放置任务流程搭建。

## 主要特性
1.  支持两种主流深度学习抓取方案：
    - 基于GPD的点云抓取位姿采样
    - 基于Dex-Net的深度图像抓取位姿采样
2.  提供可直接在MoveIt任务构造器中调用的抓取生成任务模块，快速搭建拾取放置流水线
3.  配套完整的安装部署教程与演示启动流程。
