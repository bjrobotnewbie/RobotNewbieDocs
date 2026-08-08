# FMT-Model

- 项目链接：https://github.com/Firmament-Autopilot/FMT-Model

## 项目概述

FMT-Model (Firmament Model) 是 [Firmament Autopilot](https://github.com/Firmament-Autopilot) 项目的一部分，这是一个**固定翼无人机 MATLAB/Simulink 仿真框架**，包含完整的算法库。

FMT-Model 为固定翼飞控开发提供了完整的仿真环境，方便在 MATLAB/Simulink 中快速开发和测试飞控算法。

### 架构组成

- **INS**：惯性导航系统模块
- **FMS**：飞行管理系统模块
- **Controller**：控制器模块
- **Plant**：飞行器动力学模型

### 环境要求

- 推荐 MATLAB 2018b 或更高版本
- 需要的工具箱：
  - Aerospace Blockset
  - Embedded Coder
  - Instrument Control Toolbox
  - Simulink 3D Animation
  - Simulink Coder

### 主要特点

- 完整的固定翼无人机动力学模型
- 包含导航、制导、控制全套算法
- 基于 Simulink 模块化设计，易于修改
- 支持代码生成，可以直接部署到嵌入式平台
- 开源 GPL 许可证

如果你使用 MATLAB/Simulink 开发固定翼飞控算法，FMT-Model 是一个很好的起点。
