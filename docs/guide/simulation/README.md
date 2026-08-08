# 仿真与模拟

仿真与模拟技术是机器人开发过程中的重要工具，可以在虚拟环境中测试机器人算法、控制策略和系统性能，无需实际硬件，大大降低开发成本和风险。本章节涵盖主流的仿真器、物理引擎、仿真环境与基准平台。

## 分类说明

| 分类 | 主要内容 | 典型项目 |
|------|---------|---------|
| **物理引擎** | 刚体/柔体动力学仿真底层引擎 | MuJoCo, Bullet, DART, Drake, Newton |
| **通用机器人仿真器** | 完整仿真环境与开发工具 | Gazebo, CoppeliaSim, Webots, PyBullet |
| **NVIDIA 仿真生态** | 基于 Isaac Sim 的仿真平台 | Isaac Sim, Isaac Lab, IsaacGym |
| **无人机/航空仿真** | 飞行器仿真环境 | AirGym, AirSim360, Cosys-AirSim, crazyflow |
| **具身AI仿真平台** | 面向具身智能的仿真平台 | Genesis, Habitat-Sim, GenieSim |
| **操作仿真与基准** | 机器人操作任务仿真与评测 | ManiSkill, Metaworld, robosuite, SAPIEN |
| **RL/学习仿真框架** | 结合RL训练的仿真框架 | dm_control, ML-Agents, MJLab, UniLab |

## 项目列表

### 物理引擎

- [Bullet Physics SDK](/guide/simulation/bullet-physics/README) - 开源物理引擎，支持刚体和柔体仿真
- [DART](/guide/simulation/dart/README) - 动态动画与机器人工具箱，多刚体动力学仿真
- [Drake](/guide/simulation/drake/README) - MIT机器人软件开发平台，建模/仿真/控制/分析工具链
- [MuJoCo](/guide/simulation/mujoco/README) - Google DeepMind高性能物理引擎，专注接触交互仿真
- [Newton](/guide/simulation/newton/README) - NVIDIA/DeepMind/Disney联合开发的开源物理引擎
- [Chrono](/guide/simulation/chrono/README) - 多体动力学和多物理场仿真C++库
- [NVIDIA Warp](/guide/simulation/warp/README) - Python JIT编译框架，提供GPU加速可微计算
- [Quadrants](/guide/simulation/quadrants/README) - 高性能多平台编译器，支持CUDA/Vulkan/Metal并行计算

### 通用机器人仿真器

- [CoppeliaSim](/guide/simulation/coppeliasim/README) - 功能强大的机器人仿真平台（原V-REP）
- [Gazebo](/guide/simulation/gazebo/README) - 开源高保真3D机器人仿真器，深度集成ROS
- [GZ Sim](/guide/simulation/gz-sim/README) - Gazebo现代版（前身Ignition），支持多机器人系统仿真
- [Webots](/guide/simulation/webots/README) - 开源机器人仿真器，支持多种机器人类型
- [PyBullet](/guide/simulation/pybullet/README) - 基于Bullet的轻量级Python机器人仿真接口
- [pyrobosim](/guide/simulation/pyrobosim/README) - 支持ROS 2的2D移动机器人模拟器
- [ir-sim](/guide/simulation/ir-sim/README) - 基于Python的轻量级智能机器人模拟器
- [MVSIM](/guide/simulation/mvsim/README) - 轻量级2.5D动力学模拟器，支持多智能体

### NVIDIA 仿真生态

- [Isaac Sim](/guide/simulation/IsaacSim/README) - NVIDIA基于Omniverse的机器人仿真/训练/验证平台
- [IsaacGym](/guide/simulation/isaacgym/README) - NVIDIA GPU加速RL仿真环境（已停更）
- [InternUtopia](/guide/simulation/internutopia/README) - 基于Isaac Sim的具身AI研究平台
- [ROBOTIS Lab](/guide/simulation/robotis_lab/README) - 基于Isaac Lab的ROBOTIS机器人RL/IL实验环境

### 无人机与航空仿真

- [AirGym](/guide/simulation/AirGym/README) - 基于IsaacGym的四旋翼无人机深度强化学习平台
- [AirSim360](/guide/simulation/AirSim360/README) - 基于UE5的无人机360°全景高保真仿真平台
- [Cosys-AirSim](/guide/simulation/Cosys-AirSim/README) - 基于UE的开源无人机/汽车模拟器
- [Project AirSim](/guide/simulation/ProjectAirSim/README) - 微软AirSim延续项目，基于UE5高保真仿真
- [gym-pybullet-drones](/guide/simulation/gym-pybullet-drones/README) - 基于PyBullet的四旋翼多智能体RL仿真环境
- [crazyflow](/guide/simulation/crazyflow/README) - 基于JAX的四旋翼GPU加速可微仿真器
- [multi_uav_simulator](/guide/simulation/multi_uav_simulator/README) - 基于ROS的轻量多无人机仿真器
- [BlueSky](/guide/simulation/bluesky/README) - 开源航空交通模拟器，用于ATM研究

### 自动驾驶仿真

- [CARLA](/guide/simulation/carla/README) - 开源自动驾驶研究模拟器
- [Open Simulation Interface](/guide/simulation/open-simulation-interface/README) - 自动驾驶仿真通用环境感知接口标准

### 具身AI仿真平台

- [Genesis](/guide/simulation/genesis/README) - 通用机器人/具身AI物理平台，含自研物理引擎
- [Genesis World](/guide/simulation/genesis-world/README) - 面向Physical AI的通用仿真平台
- [Genesis Nyx](/guide/simulation/genesis-nyx/README) - Genesis World的GPU加速路径追踪渲染器
- [Habitat-Sim](/guide/simulation/habitat-sim/README) - Meta AI高性能3D物理仿真器，专为具身AI设计
- [GenieSim](/guide/simulation/geniesim/README) - 智元机器人具身智能仿真平台
- [SPEAR](/guide/simulation/spear/README) - 照片级真实感具身AI研究仿真器

### 机器人操作仿真与基准

- [ManiSkill](/guide/simulation/ManiSkill/README) - 基于SAPIEN的GPU并行机器人操作仿真与基准
- [Metaworld](/guide/simulation/Metaworld/README) - 50+机器人操作任务的多任务/元RL基准
- [robosuite](/guide/simulation/robosuite/README) - 基于MuJoCo的模块化机器人学习仿真框架
- [RoboCasa](/guide/simulation/robocasa/README) - 365个任务+厨房场景的大规模仿真基准
- [SAPIEN](/guide/simulation/sapien/README) - 高性能物理仿真平台，专注机器人操作
- [SOFA](/guide/simulation/sofa/README) - 实时物理仿真框架，擅长软体/变形体仿真
- [MuJoCo Menagerie](/guide/simulation/mujoco_menagerie/README) - MuJoCo高质量机器人模型集合

### RL与学习仿真框架

- [dm_control](/guide/simulation/dm_control/README) - DeepMind基于MuJoCo的RL仿真环境
- [ML-Agents](/guide/simulation/ml-agents/README) - Unity机器学习代理工具包
- [MJLab](/guide/simulation/mjlab/README) - 结合Isaac Lab API与MuJoCo Warp的RL研究框架
- [LuckyRobots](/guide/simulation/luckyrobots/README) - LuckyEngine机器人仿真Python SDK
- [UniLab](/guide/simulation/UniLab/README) - 仿真与训练解耦的异构计算架构
- [SIMPLE](/guide/simulation/SIMPLE/README) - 人形机器人loco-manipulation策略学习与评估环境
- [ProtoMotions](/guide/simulation/ProtoMotions/README) - NVIDIA数字人运动学习GPU加速仿真框架

### 特殊仿真环境

- [ViZDoom](/guide/simulation/ViZDoom/README) - 基于Doom引擎的视觉RL研究环境
- [FMT-Model](/guide/simulation/FMT-Model/README) - 固定翼无人机MATLAB/Simulink仿真框架
- [MSS](/guide/simulation/MSS/README) - 海洋控制系统MATLAB/Simulink仿真工具箱
- [FlyGym](/guide/simulation/flygym/README) - 果蝇高保真数字孪生仿真环境
- [Elodin](/guide/simulation/elodin/README) - 飞行器软件栈仿真-飞行闭环工具链
- [LW-BenchHub](/guide/simulation/LW-BenchHub/README) - 基于Isaac Lab的具身AI统一基准平台
- [aerial-autonomy-stack](/guide/simulation/aerial-autonomy-stack/README) - 多无人机自主飞行一体化软件栈
- [Cloisim](/guide/simulation/cloisim/README) - 基于Unity 6的高性能多机器人模拟器
- [NeRD](/guide/simulation/nerd/README) - 神经机器人动力学模拟框架
- [EmbodiedGen](/guide/simulation/EmbodiedGen/README) - 面向具身智能的生成式3D世界引擎，含Image-to-3D/Text-to-3D/场景生成
- [HighwayEnv（用于自动驾驶与战术决策任务的环境集合）](/guide/simulation/HighwayEnv/README)
- [brax（基于加速器硬件的大规模并行刚体物理仿真。）](/guide/simulation/brax/README)
- [RoboTwin（RoboTwin 2.0 官方仓库）](/guide/simulation/RoboTwin/README)
- [mujoco_playground（一个用于GPU加速机器人学习与仿真到真实…）](/guide/simulation/mujoco_playground/README)
- [godot_rl_agents（这是一个开源包，为电子游戏开发者、AI研…）](/guide/simulation/godot_rl_agents/README)
- [TienKung-Lab（天宫实验室：面向足式机器人的直接Isaa…）](/guide/simulation/TienKung-Lab/README)
- [awesome-isaac-gym（精选的优秀NVIDIA Isaac Gy…）](/guide/simulation/awesome-isaac-gym/README)
- [WheeledLab（与IsaacLab集成的开源移动机器人环…）](/guide/simulation/WheeledLab/README)
- [habitat-gs（[ECCV 2026] Habitat-…）](/guide/simulation/habitat-gs/README)
- [AirSim（由微软AI与研究部门打造、基于Unrea…）](/guide/simulation/AirSim/README)
- [Minigrid（用于强化学习的简单易配置网格世界环境）](/guide/simulation/Minigrid/README)
- [go2_omniverse（支持宇树Unitree Go2、Unit…）](/guide/simulation/go2_omniverse/README)
- [SimWorld（SimWorld：面向物理与社交世界中自…）](/guide/simulation/SimWorld/README)
- [robohive（面向机器人学习的统一框架）](/guide/simulation/robohive/README)
- [robotic_arm_environment（适用于强化学习的Doosan机械臂在Ga…）](/guide/simulation/robotic_arm_environment/README)
- [FreeAskWorld（[AAAI 2026 口头报告] Fre…）](/guide/simulation/FreeAskWorld/README)
- [littlenavmap（Little Navmap 是一款适用于…）](/guide/simulation/littlenavmap/README)
- [Damn-Vulnerable-Drone（Damn Vulnerable Dron…）](/guide/simulation/Damn-Vulnerable-Drone/README)
- [pace-sim2real（PACE：一种用于足式机器人仿真到真实迁…）](/guide/simulation/pace-sim2real/README)
- [InstinctMJ（适用于人形机器人RL与Project-I…）](/guide/simulation/InstinctMJ/README)
- [simbody（高性能 C++ 多体动力学/物理库，用于…）](/guide/simulation/simbody/README)
- [CarlaAir（CarlaAir：在 CARLA 世界中…）](/guide/simulation/CarlaAir/README)
- [PegasusSimulator（基于 NVIDIA Isaac Sim …）](/guide/simulation/PegasusSimulator/README)
- [IsaacLab（基于 NVIDIA Isaac Sim …）](/guide/simulation/IsaacLab/README)
- [SAPIEN（SAPIEN 具身智能平台）](/guide/simulation/SAPIEN/README)
- [metaurban（[ICLR 2025 焦点] MetaU…）](/guide/simulation/metaurban/README)
