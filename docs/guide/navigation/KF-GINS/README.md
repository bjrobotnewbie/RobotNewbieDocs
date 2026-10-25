# KF-GINS

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/KF-GINS/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

- GitHub仓库: https://github.com/i2Nav-WHU/KF-GINS

## 项目概述
KF-GINS是一个基于扩展卡尔曼滤波（EKF）的GNSS/INS组合导航系统，由武汉大学i2Nav团队开发。该系统实现了GNSS定位结果与IMU数据的经典组合导航解算，作为《惯性导航原理与GNSS/INS组合导航》课程的配套资源。系统采用C++开发，使用CMake管理项目，包含21维误差状态向量，支持IMU误差补偿、惯性导航解算、卡尔曼滤波、误差反馈等功能，适用于机器人导航、自动驾驶等领域的组合导航研究和开发。
