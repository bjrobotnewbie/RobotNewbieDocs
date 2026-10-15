# PteroSim-UAV-Simulator

无人机仿真平台，用于开发、测试与科研。

## 项目链接

- GitHub: <https://github.com/PteroLabsAI/PteroSim-UAV-Simulator>
- 项目主页: <https://pterolabs.ai/>

## 项目介绍
PteroSim是一款无人机（UAV）仿真平台，主要用于无人机的开发、测试与研究工作，支持PX4、ArduPilot等主流飞控的SITL仿真，具备可编程API，可满足多无人机协同等场景的仿真需求。

## 主要特性
1. 提供高精度6自由度（6-DOF）飞行动力学模型，支持最高10倍实时仿真
2. 内置风场与湍流建模功能
3. 原生支持PX4、ArduPilot SITL仿真，兼容多旋翼、直升机、VTOL、固定翼等多种机型
4. 集成IMU、GPS、气压计、空速计、相机等多种传感器仿真
5. 飞行器模型基于JSBSim XML定义，支持自定义机型扩展
6. 提供可编程gRPC API，支持多无人机协同编排
7. 配套Python SDK，可通过`pip install pterosim`快速安装使用
