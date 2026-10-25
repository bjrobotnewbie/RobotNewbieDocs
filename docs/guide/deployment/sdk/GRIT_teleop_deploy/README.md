# GRIT_teleop_deploy

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/deployment/sdk/GRIT_teleop_deploy/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

本仓库提供 Unitree G1 机器人的 GRIT v0.0.1 部署代码，这是一种用于全身运动追踪的人形机器人控制算法。

## 项目链接

- GitHub: <https://github.com/mrzuang/GRIT_teleop_deploy>

## 项目介绍
本项目为GRIT v0.0.1算法提供Unitree G1人形机器人部署代码，GRIT是一款人形机器人全身运动跟踪控制算法，通过统一UDP接口完成策略推理，支持利用PICO设备实现操作员全身运动的跟踪控制，同时提供仿真与实机部署相关工具。

## 主要特性
1. 包含GRIT ONNX策略及部署契约
2. 提供50Hz Python推理与控制运行时
3. 支持无头及交互式MuJoCo仿真环境（sim2sim）
4. 支持PICO/XRoboToolkit实时运动重定向
5. 集成原生Unitree SDK2硬件桥接，具备过时命令看门狗功能
6. 提供轨迹跟踪泛化、遥操作等演示场景，支持仿真与实机部署

项目运行需满足Ubuntu 22.04/24.04系统、Python 3.10、uv、MuJoCo等依赖，支持通过MuJoCo仿真快速启动验证。
