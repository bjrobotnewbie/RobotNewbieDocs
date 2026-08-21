# 机器人控制

机器人控制是机器人技术的核心，研究如何通过算法和硬件系统实现机器人的运动控制、力控制和智能决策。本章节涵盖控制理论基础、全身控制、最优控制、飞控固件和控制框架。

## 分类说明

| 分类 | 主要内容 | 典型项目 |
|------|---------|---------|
| **控制理论教材** | 经典/现代/鲁棒控制理论 | 自动控制原理, 现代控制工程, 鲁棒控制 |
| **全身控制与 Locomotion** | 人形/腿足机器人运动控制 | GR00T-WBC, MultiModalWBC, IHMC |
| **最优控制与 MPC** | DDP/MPC/MPPI 等最优控制算法 | crocoddyl, px4-mpc, mppi_playground |
| **飞控固件** | 无人机/地面机器人飞控 | PX4, ArduPilot, INAV, madflight |
| **控制框架** | 通用控制框架与工业控制 | ros2_control, LinuxCNC |
| **遥操作与机器人 SDK** | 机器人遥操作与厂商控制 SDK | Teleopit, EngineAI SDK |

## 项目列表

### 控制理论教材与课程

- [自动控制原理](/guide/control/automatic-control-theory/README) - 胡寿松《自动控制原理》第八版，涵盖经典与现代控制理论
- [现代控制工程](/guide/control/modern-control-engineering/README) - 尾形克彦《现代控制工程》第五版，状态空间与最优控制
- [现代控制系统](/guide/control/modern-control-system/README) - 多尔夫《现代控制系统》第14版，含MATLAB/LabVIEW应用
- [鲁棒控制基础理论](/guide/control/robust-control-theory/README) - 苏宏业等著，涵盖H∞/μ分析/LMI/多智能体协同
- [MIT 6.832 Underactuated Robotics](/guide/control/mit-6832/README) - MIT欠驱动机器人学课程，非线性动力学与控制

### 全身控制与 Locomotion

- [GR00T-WholeBodyControl](/guide/control/GR00T-WholeBodyControl/README) - NVIDIA人形机器人全身控制平台，解耦式WBC+RL+IK
- [MultiModalWBC (M3imic)](/guide/control/MultiModalWBC/README) - 基于IsaacLab的腿足机器人多模态全身控制框架
- [bipedal-locomotion-framework](/guide/control/bipedal-locomotion-framework/README) - 人形机器人双足行走C++算法库
- [ihmc-open-robotics-software](/guide/control/ihmc-open-robotics-software/README) - IHMC人形机器人平衡控制与步态控制算法库
- [Quadruped-PyMPC](/guide/control/Quadruped-PyMPC/README) - 四足机器人MPC控制器，支持ACADOS和JAX求解

### 最优控制与 MPC

- [crocoddyl](/guide/control/crocoddyl/README) - 接触序列下机器人最优控制库，基于DDP求解器
- [px4-mpc](/guide/control/px4-mpc/README) - 基于acados的PX4无人机MPC控制器
- [mppi_playground](/guide/control/mppi_playground/README) - 基于PyTorch的MPPI算法实现库，GPU加速
- [crisp_controllers](/guide/control/crisp_controllers/README) - ROS2机械臂柔顺力矩控制器，笛卡尔阻抗控制

### 飞控固件

- [PX4 Autopilot](/guide/control/px4/README) - 开源自动驾驶固件，支持无人机和地面机器人
- [ArduPilot](/guide/control/ardupilot/README) - 开源飞控固件，支持多旋翼/固定翼/rover/船
- [INAV](/guide/control/inav/README) - 开源飞控固件，支持多类型无人机/航模导航与飞行控制
- [madflight](/guide/control/madflight/README) - 低成本开发板(ESP32/RP2040/STM32)飞控构建工具包

### 控制框架与工业控制

- [ros2_control](/guide/control/ros2_control/README) - ROS 2通用机器人控制框架，统一硬件接口与模块化控制器
- [LinuxCNC](/guide/control/linuxcnc/README) - 开源数控机床控制系统，支持铣床/车床/3D打印/机器人手臂

### 遥操作与机器人 SDK

- [PX4-Autopilot（PX4 自动驾驶仪软件）](/guide/control/PX4-Autopilot/README)
- [OpenKAI（OpenKAI：一个用于无人载具与机器人…）](/guide/control/OpenKAI/README)
- [RMCS（基于ROS2的RoboMaster控制系…）](/guide/control/RMCS/README)
- [PBHC（论文《KungfuBot：基于物理的人形…）](/guide/control/PBHC/README)
- [mpx（基于JAX的模型预测控制）](/guide/control/mpx/README)
- [wb_humanoid_mpc（全身非线性模型预测控制：实时人形机器人定…）](/guide/control/wb_humanoid_mpc/README)
- [panda-py（Python 绑定，用于实时控制 Fra…）](/guide/control/panda-py/README)
- [Pontryagin-Differentiable-Programming（能够学习控制系统的（神经）控制目标函数、…）](/guide/control/Pontryagin-Differentiable-Programming/README)
