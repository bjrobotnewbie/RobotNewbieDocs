# tianracer

基于 NVIDIA 开发套件构建的tianbot自主AI赛车元包。

## 项目链接

- GitHub: <https://github.com/tianbot/tianracer>
- 中文文档: https://github.com/tianbot/tianracer/blob/master/README_CN.md

## 项目介绍
Tianracer是基于NVIDIA开发套件打造的低成本自主AI赛车元套件，涵盖1:10到1:5尺寸的系列车型，采用闭环速度控制，可精准跟随输入指令。基础版最高时速3m/s，专业版可达10m/s。
项目基于Jetracer升级AI能力，目标实现除基础建图、定位、导航外的目标检测、交通灯识别、车道保持等进阶功能，同时提供Gazebo仿真环境用于开发测试。用户可通过官方淘宝店购买预装软硬件的成品赛车。

## 主要特性
1.  硬件适配广泛：支持Jetson Nano/TX2/Xavier/Orin等NVIDIA开发板，搭配BLDC电机、多品牌激光雷达、1080P摄像头等配件
2.  支持闭环速度控制，操控精度更高
3.  提供完整的ROS功能包，内置Gazebo仿真环境，包含多种快速启动的launch文件，可快速验证机器人、导航、定位等功能
4.  支持多场景自动驾驶进阶功能开发
