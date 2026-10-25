# imu_gps_localization

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/navigation/imu_gps_localization/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

使用卡尔曼滤波融合IMU和GPS数据以实现定位。

## 项目链接

- GitHub: <https://github.com/ydsf16/imu_gps_localization>
- 项目主页: <https://zhuanlan.zhihu.com/p/152662055>

## 项目介绍
imu_gps_localization是一个基于误差状态卡尔曼滤波（EKF）的定位项目，核心功能是融合IMU与GPS数据实现全局定位，代码实现参考了《Quaterniond kinematics for the error-state Kalman filter》相关理论，支持在ROS环境下的机器人定位场景，可结合公开数据集（如UTBM Robocar Dataset）进行测试验证，遵循GPLv3开源协议。

## 主要特性
1. 采用误差状态卡尔曼滤波算法，融合IMU与GPS数据完成全局定位
2. 代码实现基于权威理论文献，算法逻辑严谨
3. 提供公开数据集适配，便于开发者测试验证
4. 开源协议为GPLv3，支持非商业自由使用，商业使用可联系作者咨询授权
