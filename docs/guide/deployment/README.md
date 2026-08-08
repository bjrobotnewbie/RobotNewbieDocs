# 机器人部署

机器人部署是将开发完成的机器人系统和算法部署到实际硬件平台并运行的过程，包括模型优化、系统集成和实际测试。本章节涵盖机器人部署的全栈技术方案，从边缘设备到云端，从单机器人到集群部署。

## 分类导航

### 🤖 机器人系统集成

专门为机器人设计的部署框架，支持 ROS 2 集成、自动驾驶 MLOps 闭环。

| 项目 | 核心特性 | 机器人平台 | 适用场景 |
| ---- | -------- | ---------- | -------- |
| [AWML](/guide/deployment/awml/README) | Autoware MLOps, 18+ 量产模型, ROS2 生态 | 自动驾驶 / 无人车 | 感知模型训练-部署全流程 |
| [Isaac ROS Deploy](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_deploy) | ROS 2 原生, LEAPP 导出, 安全控制器, 实时推理 | NVIDIA Jetson / x86 | 仿真到真实策略部署, 具身智能 |
| [Isaac ROS](https://github.com/NVIDIA-ISAAC-ROS) | NVIDIA 官方, GPU 加速感知, GMSL 相机支持 | NVIDIA Jetson 全系 | 视觉感知, 导航, 操作 |
| [MoveIt 2](https://github.com/moveit/moveit2) | 机械臂运动规划, 碰撞检测, 轨迹优化 | 工业机械臂 | 工业操作, 抓取规划 |
| [Nav2](https://github.com/ros-navigation/navigation2) | ROS 2 导航框架, 路径规划, 避障 | 移动机器人 | 自主导航, SLAM |

> **Isaac ROS Deploy** 提供从 NVIDIA Isaac Lab 训练的策略到真实机器人的完整部署流水线，支持 `ros2_control` 实时控制循环和 `ros2_nodes` 多模型推理，是 2026 年具身智能部署的重要工具。

### 🌐 跨平台与分布式

支持多种硬件后端和大规模部署的通用框架。

| 项目 | 核心特性 | 硬件支持 | 适用场景 |
| ---- | -------- | -------- | -------- |
| [ONNX Runtime](/guide/deployment/onnx-runtime/README) | 跨平台, 算子融合, 多后端 | CPU/GPU/NPU | 通用模型部署 |
| [OpenVINO](/guide/deployment/openvino/README) | Intel 优化, NNCF 量化, 工具链 | CPU/iGPU/VPU | 工业机器人 |
| [Ray Serve](/guide/deployment/ray-serve/README) | 分布式, 自动扩缩容, 流量灰度 | 集群节点 | 大规模机器人集群 |

## 技术选型指南

### 按硬件平台选择

| 硬件平台 | 推荐方案 | 关键优化点 |
| -------- | -------- | ---------- |
| **NVIDIA Jetson Thor (T5000/T4000)** | TensorRT Edge-LLM + FP8/NVFP4 | 功耗模式调优, 内存优化, VLA 模型实时推理 |
| **NVIDIA Jetson Orin** | TensorRT + ONNX Runtime | GPU 内存池, 算子融合, Isaac ROS 集成 |
| **NVIDIA Jetson Xavier** | TensorRT + AWQ 4bit | GPU 内存池, 算子融合 |
| **Intel CPU/x86** | OpenVINO + ONNX Runtime | INT8 量化, 多线程优化 |
| **ARM 嵌入式 (Raspberry Pi)** | llama.cpp + Q4_K_M 量化 | 二进制体积优化, 零 Python 依赖 |
| **数据中心 A100/H100** | TensorRT-LLM + vLLM | FP8, 张量并行, PagedAttention |
| **消费级 GPU (RTX 3090/4090/5080)** | LMDeploy + AWQ 4bit / llama.cpp CUDA | 显存占用最小化 |

> **Jetson Thor** 是 NVIDIA 2025 年发布的专为物理 AI 和人形机器人打造的高性能平台，T5000 提供高达 2070 FP4 TFLOPS 算力和 128GB 显存，T4000 提供 1200 FP4 TFLOPS 和 64GB 显存，均已支持 TensorRT Edge-LLM 进行 VLA 模型部署。

### 按应用场景选择

| 应用场景 | 推荐方案 | 说明 |
| -------- | -------- | ---- |
| **人形机器人 VLA 部署** | Jetson Thor + TensorRT Edge-LLM + Isaac ROS Deploy | 支持 GR00T N1.6 等 VLA 模型的实时推理 |
| **移动机器人导航** | ROS 2 + Nav2 + Isaac ROS (视觉感知) | 完整的感知-规划-控制闭环 |
| **工业机械臂操作** | ROS 2 + MoveIt 2 + OpenVINO (视觉检测) | 精确的运动规划与视觉引导 |
| **边缘端隐私推理** | llama.cpp / Ollama | 数据不出设备，零云端依赖 |
| **大规模机器人集群** | Ray Serve + Kubernetes | 统一调度，自动扩缩容 |
| **快速原型验证** | Ollama + ROS 2 | 一键启动，快速迭代 |

## 具身智能部署趋势（2026）

### VLA 模型部署

2025-2026 年，具身智能大模型（VLA）成为机器人部署的核心方向。

部署这些模型通常需要：

1. 使用 **Isaac Lab** 进行仿真训练
2. 通过 **LEAPP** 导出 ONNX 策略图
3. 使用 **Isaac ROS Deploy** 部署到真实机器人
4. 在 **Jetson Thor** 上通过 **TensorRT Edge-LLM** 运行推理

### 仿真到真实（Sim-to-Real）

| 工具 | 功能 | 链接 |
| ---- | ---- | ---- |
| Isaac Lab | NVIDIA 强化学习训练平台 | [github.com/isaac-sim/IsaacLab](https://github.com/isaac-sim/IsaacLab) |
| Isaac ROS Deploy | 策略部署到真实机器人 | [github.com/NVIDIA-ISAAC-ROS/isaac\_ros\_deploy](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_deploy) |
| MuJoCo | 物理仿真引擎 | [github.com/google-deepmind/mujoco](https://github.com/google-deepmind/mujoco) |

- [ogma（面向飞行器与机器人应用的运行时监视器生成…）](/guide/deployment/ogma/README)

- [rosclaw（面向Physical AI与具身智能体的…）](/guide/deployment/rosclaw/README)

- [LeggedSkillDeploy（一个用于基于强化学习的足式机器人运动控制…）](/guide/deployment/LeggedSkillDeploy/README)

- [robonix（具身人工智能操作系统（EAIOS））](/guide/deployment/robonix/README)
