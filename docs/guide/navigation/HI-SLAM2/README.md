# HI-SLAM2

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/HI-SLAM2/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

HI-SLAM2: 基于高斯分布的几何感知 SLAM，用于快速单目场景重建

## 项目链接

- GitHub: <https://github.com/Willyzw/HI-SLAM2>
- 项目主页: <https://hi-slam2.github.io/>

## 项目介绍
HI-SLAM2是一款几何感知的高斯SLAM系统，核心功能是基于单目输入快速构建3DGS地图，可生成精确的网格重建结果与高质量渲染图像。该系统在几何精度、渲染质量上均优于现有单目SLAM方法，同时具备更快的运行速度，支持语义重建等扩展功能，可通过Conda环境配置与CUDA内核编译完成部署。

## 主要特性
1. 基于单目输入实现快速3D场景重建，构建3DGS地图
2. 兼顾几何精度与渲染质量，性能优于现有单目SLAM方法
3. 支持语义重建扩展功能
4. 提供完整的部署流程，包含子模块克隆、Conda环境配置、CUDA内核编译步骤
