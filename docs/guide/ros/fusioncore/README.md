# fusioncore

FusionCore 是面向真实机器人运行的 ROS 2 UKF 传感器融合 SDK，融合 IMU、轮速计和 GPS 等数据。

## 项目链接

- GitHub: <https://github.com/manankharwar/fusioncore>
- 项目主页: https://manankharwar.github.io/fusioncore/

## 项目概述

FusionCore 针对真实机器人定位中的常见问题设计，包括标定不准、时间戳抖动、GPS 延迟、轮胎打滑和 ARM 硬件部署等。它使用 UKF 算法进行 3D 传感器融合，支持 IMU、wheel encoders、GPS 约 100Hz 的融合流程，并提供 ROS 2 包、Docker 快速体验和一键测试脚本。

项目适合移动机器人、UGV 和户外机器人平台使用，尤其是需要在工程现场快速获得稳定状态估计但不希望大量手动调参的场景。相比通用滤波示例，FusionCore 更强调真实硬件鲁棒性、快速验证和 ROS 2 原生集成。
