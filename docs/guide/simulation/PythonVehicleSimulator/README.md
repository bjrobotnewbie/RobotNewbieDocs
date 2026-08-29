# PythonVehicleSimulator

Python 车辆模拟器是补充教科书《海洋船舶水动力学与运动控制手册》（第 2 版，T. I. Fossen 著，2021 年由 John Wiley & Sons Ltd 出版）的软件。

## 项目链接

- GitHub: <https://github.com/cybergalactic/PythonVehicleSimulator>
- 项目主页: <https://python.fossen.biz>

## 项目介绍
本项目是Python船舶运动模拟器，作为《Handbook of Marine Craft Hydrodynamics and Motion Control》（第2版）配套辅助软件，同时补充MATLAB的MSS（Marine Systems Simulator）工具箱。
项目支持AUV、USV和船舶三类载具的建模，所有载具均以Python对象形式封装，自带导航、制导与控制相关方法，通过`main.py`可启动实时仿真，还可生成3D动画可视化仿真过程。

## 主要特性
1.  内置多款成熟载具模型：包括DSRV、护卫舰、Otter USV、Remus100 AUV、油轮等共10种不同类型的水面/水下船舶模型
2.  模块化代码架构：分为主程序、通用GNC工具、控制、制导、仿真循环、绘图动画等库文件
3.  完全基于Fossen教授的经典船舶动力学建模理论，可作为船舶运动控制、SLAM、RL相关教学与开发的仿真平台。

### 依赖要求
需要安装numpy、matplotlib、pytest三方库。
