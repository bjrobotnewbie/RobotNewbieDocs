# Ground-Challenge

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/benchmark_data/Ground-Challenge/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

聚焦于边缘情况的多传感器 SLAM 数据集（ROBIO2023）

## 项目链接

- GitHub: <https://github.com/sjtuyinjie/Ground-Challenge>

## 项目介绍
Ground-Challenge是面向地面机器人的多传感器SLAM数据集，聚焦SLAM系统的极端场景（corner cases），由配备RGB-D相机、IMU、轮式里程计、3D激光雷达的地面机器人采集，包含36条轨迹，旨在为视觉SLAM的极端场景研究提供支撑，相关成果发表于ROBIO2023。

## 主要特性
1. 多传感器信息丰富，涵盖RGBD、轮式、IMU等数据；
2. 包含多种SLAM极端场景，如剧烈运动、严重遮挡、光照变化、纹理稀疏、纯旋转、运动模糊、轮式悬空等；
3. 可用于测试现有主流SLAM算法（如VINS-Mono、ORB-SLAM3、VINS-RGBD等），能有效验证算法在极端场景下的性能，助力学术研究。
