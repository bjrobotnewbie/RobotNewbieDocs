# lerobot_android

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/deployment/lerobot_android/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

使用 Android 手机作为 LeRobot 移动机器人的控制器替代 Raspberry Pi。其成本更低，且自带屏幕、USB 摄像头、GPS、Wi-Fi、5G 及 NPU。

## 项目链接

- GitHub: <https://github.com/llros007/lerobot_android>
- 中文文档: https://github.com/llros007/lerobot_android/blob/main/README.zh-CN.md

## 项目介绍
lerobot_android 是一款将安卓手机作为 LeRobot 移动机器人控制器的开源项目，替代树莓派使用，成本更低。项目基于 Hugging Face LeRobot v0.6.1 版本开发，包含手机端应用与 PC 端工具，支持通过 USB OTG 连接 USB 摄像头、舵机控制板等外设，无需 root 即可直接使用，适配 LeRobot 数据集格式，支持机器人遥操作与数据录制。

## 主要特性
1. 核心功能：支持通过 PC 端 SO-101 主臂遥操作机器人单臂，同时可通过键盘控制差速驱动底盘；能以 720p、30fps 录制包含关节位置、底盘速度及手机/USB 摄像头画面的数据集。
2. 技术优势：手机端直接处理 USB 串口通信，30Hz 控制循环，采用 MJPEG 流传输摄像头画面，避免 Wi-Fi 延迟影响控制性能；利用手机自带的屏幕、摄像头、NPU、GNSS、5G/Wi-Fi 等硬件，无需额外采购接线。
3. 兼容性：依赖 Python 3.12，适配 LeRobot 上游依赖，支持 ROS 2 扩展（待开发）。
