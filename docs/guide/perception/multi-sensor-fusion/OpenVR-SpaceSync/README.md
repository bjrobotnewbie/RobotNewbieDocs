# OpenVR-SpaceSync

使用 Follow SLAM HMD 模式同步 Lighthouse 设备，确保头显姿态始终权威，并持续将 Lighthouse 跟踪与头显姿态对齐。

## 项目链接

- GitHub: <https://github.com/shinyflvre/OpenVR-SpaceSync>

## 项目介绍
OpenVR-SpaceSync 是基于 OpenVR-SpaceOverride 二次开发的开源工具，采用 AGPL-3.0 协议，用于同步 Lighthouse 设备与 SLAM 头显的空间坐标系，解决跨追踪系统的漂移问题。它支持将 Lighthouse 追踪设备（如 Vive/Tundra 追踪器、Index 控制器、基站）与各类 SLAM 头显（如 Galaxy XR、Quest、Pico，可通过 Virtual Desktop、Steam Link、ALVR 等串流）的空间位置对齐，需在头显上安装至少 1 个追踪器，实现跨追踪系统的实时位姿校准。

## 主要特性
1. 提供两种运行模式：
   - 追踪器驱动头显模式：校准后以头显追踪器位姿为基准构建头显位姿，适合串流完全同步 SteamVR 渲染画面的场景；
   - Follow SLAM HMD 模式：保留头显自身 SLAM 位姿的权威性，仅用头显追踪器测量 SLAM 空间与 Lighthouse 空间的偏移并实时对齐，可避免追踪中断后出现的视角旋转、黑边、手部错位等问题，重定位时仅追踪器会小幅跳动后恢复；
2. 两种模式共享同一校准数据，切换仅需勾选选项，无需重新校准；
3. 采用后台滚动采样缓冲实现连续校准，解决传统单次校准的空间漂移问题，适配多种 Lighthouse 设备与 SLAM 头显组合。
