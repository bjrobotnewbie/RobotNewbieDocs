# DPVO

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/DPVO/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

深度特征视觉定位/SLAM

## 项目链接

- GitHub: <https://github.com/princeton-vl/DPVO>

## 项目介绍
DPVO是基于两篇顶刊顶会论文实现的深度补丁视觉里程计/视觉SLAM（SLAM）项目，由普林斯顿视觉实验室开发。项目提供了完整的源代码，支持通过Colab在线试用，也提供了Docker部署方案。

## 主要特性
1.  **核心功能**：实现基于深度学习的视觉里程计和闭环视觉SLAM，支持单目、双目序列输入，输出相机位姿与场景重建结果。
2.  **环境适配**：已在Ubuntu 20/22、CUDA 11/12环境下完成测试。
3.  **可选扩展**：
    - 支持Pangolin可视化工具，可实时查看位姿与重建效果
    - 可选安装经典闭环后端，适配大场景闭环检测
4.  **使用场景**：适用于机器人导航、自主驾驶、三维重建等需要实时视觉定位与建图的场景。
