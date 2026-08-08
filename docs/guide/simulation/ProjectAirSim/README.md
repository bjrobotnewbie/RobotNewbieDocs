# ProjectAirSim

Project AirSim 是 AirSim 的延续和演进，用于无人机、机器人和自主系统的高保真仿真。

## 项目链接

- GitHub: <https://github.com/iamaisim/ProjectAirSim>
- 项目主页: https://iamaisim.github.io/ProjectAirSim/

## 项目概述

Project AirSim 由原微软 AirSim 项目工程师组成的 IAMAI Simulations 推动，基于 Unreal Engine 5 提供照片级视觉，并支持自定义物理、控制器、执行器和传感器集成。它面向无人机、机器人和其他自主系统的构建、训练和测试，是对微软停止维护 AirSim 后相关生态的延续。

项目架构分为基础仿真库、Unreal 插件和客户端库三层：底层描述通用机器人结构和仿真 tick loop，中间层连接物理/控制/渲染组件，客户端库则通过网络 API 与机器人和场景交互。它适合无人机视觉感知、导航控制、自动驾驶和高真实感数据生成等研究与工程场景。
