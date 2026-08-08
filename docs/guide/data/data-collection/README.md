# 机器人数据采集

机器人数据采集是机器人学习的基础环节，高质量的数据是训练出优秀机器人智能体的前提。本章节涵盖动作捕捉系统、遥操作采集等主流数据采集技术和开源项目。

## 动作捕捉系统

动作捕捉系统用于获取人体或机器人关节运动数据，是机器人模仿学习和数据采集的重要基础设施。

### 项目列表

- [PNP - 六IMU人体动作捕捉](./pnp/README)：基于6个IMU的实时人体动作捕捉系统
- [FlashCap - 毫秒级精准人体动作捕捉](./flashcap/README)：基于闪烁LED和事件相机的毫秒级动作捕捉
- [DexCap - 灵巧操作可扩展便携式动作捕捉](./dexcap/README)：斯坦福李飞飞团队，灵巧操作数据采集系统
- [MiKaPo - 动态建模捕捉](./mikapo/README)：开源动态建模捕捉项目
- [EasyMocap - 简易人体动作捕捉](./easymocap/README)：浙大3DV实验室，开源易用多人动作捕捉
- [Mediapipe4u-plugin - MediaPipe动作捕捉插件](./mediapipe4u-plugin/README)：基于MediaPipe的轻量级动作捕捉，中文文档
- [XRMoCap - OpenXRLab动作捕捉](./xrmocap/README)：OpenXRLab开源动作捕捉工具链
- [EgoLocate - 自中心定位动作捕捉](./egolocate/README)：自中心视角动作捕捉方法

## 遥操作采集

遥操作采集通过人远程控制机器人收集演示数据，是模仿学习和强化学习的重要数据来源。

### 项目列表

- [XR Teleoperate - XR沉浸式遥操作](./xr-teleoperate/README)：Unitree人形机器人XR设备遥操作，1.4k+ stars
- [IsaacTeleop - NVIDIA统一遥操作](./isaac-teleop/README)：仿真和真实机器人统一遥操作框架
- [LeRobot-Anything-U-Arm - 跨形态遥操作](./lerobot-anything-uarm/README)：LeRobot跨形态遥操作
- [SPES Teleop - WebXR手机VR遥操作](./spes-teleop/README)：手机/VR变身为机器人遥操作设备
- [ROS Teleop Tools - ROS通用遥操作工具](./ros-teleop-tools/README)：ROS生态通用遥操作工具集

## 核心价值

数据采集的质量直接决定了：

- **模仿学习性能**：演示数据的质量决定了策略克隆效果
- **泛化能力**：多样化场景数据提升模型鲁棒性
- **迁移学习**：高质量数据支持跨机器人迁移
- **仿真到现实**：准确采集支持sim2real迁移

数据采集是机器人学习流水线的第一步，没有好数据就没有好模型。

- [UMI-3D（UMI-3D SLAM与数据处理流水线：…）](/guide/data/data-collection/UMI-3D/README)

- [chek-ego-miner（CHEK EGO Miner 由青空科技…）](/guide/data/data-collection/chek-ego-miner/README)
