# open-simulation-interface

Open Simulation Interface 是自动驾驶虚拟仿真中的通用环境感知接口标准，基于 Protocol Buffers 定义。

## 项目链接

- GitHub: <https://github.com/OpenSimulationInterface/open-simulation-interface>
- 项目主页: https://opensimulationinterface.github.io/osi-antora-generator/asamosi/latest/specification/index.html

## 项目概述

OSI 面向自动驾驶功能在虚拟场景中的开发和测试，提供统一的数据接口来描述环境感知信息。随着自动驾驶系统复杂度提升，虚拟测试需要可控、可复现的场景和清晰的模块边界；OSI 通过 protobuf 消息定义，使仿真器、传感器模型、自动驾驶算法和测试工具之间可以交换一致的环境、对象、车道、传感器和轨迹信息。

该项目不是具体模拟器，而是接口规范和消息定义。它适合用于联合仿真、传感器模型封装、自动驾驶功能测试和仿真工具链集成，帮助不同厂商或研究团队在虚拟测试中减少数据格式不一致带来的适配成本。
