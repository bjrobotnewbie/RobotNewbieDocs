# Kite-GC

Kite Ground Control（Kite GC）是一款面向 INAV、ArduPilot 和 PX4 航空器的现代跨平台地面控制站，支持飞机、多旋翼、垂直起降飞行器（VTOL）、直升机、轮式车辆及船只等。

## 项目链接

- GitHub: <https://github.com/b14ckyy/Kite-GC>
- 项目主页: <https://b14ckyy.github.io/Kite-GC/>

## 项目介绍
Kite Ground Control（简称Kite GC）是一款现代化跨平台地面控制站，支持INAV、ArduPilot和PX4系列飞行器（固定翼、多旋翼、VTOL、直升机）以及地面机器人、船只。它采用Tauri 2.0（Rust后端）和Svelte 5（TypeScript前端）开发，当前处于1.0正式版的功能冻结阶段，仅接受针对master分支的bug修复提交，新功能需提交至development分支。

## 主要特性
1.  **沉浸式3D飞行视图**：支持带真实地形的3D globe，可实时显示飞行器位置、航点覆盖、FPV摄像头画面以及昼夜动态光照，支持2D/3D界面无缝切换
2.  **多 autopilot 统一支持**：一套界面即可完成INAV、ArduPilot、PX4设备的规划、飞行和日志记录，支持监听和中继两种连接模式
3.  **编队、电池与任务管理**：可管理飞行器和电池库，包含完整参数表和生命周期统计，支持可复用的任务库并与飞行日志联动
4.  内置地图与实时视频叠加显示
