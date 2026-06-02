# 机器人训练

机器人训练是指通过机器学习、强化学习等方法训练机器人智能体，使其能够自主完成各种任务的过程。本章节涵盖主流的机器人训练工具和框架。

## 资源列表

- [Habitat Lab](./habitat-lab/README.md)：Meta AI开发的具身智能训练框架，支持视觉导航和室内环境交互
- [Isaac Lab](./isaaclab/README.md)：NVIDIA开发的统一机器人学习框架，支持强化学习、模仿学习等多种算法
- [LeRobot](./lerobot/README.md)：Hugging Face开发的开源机器人学习库，支持多模态机器人学习和预训练模型
- [RLlib](./rllib/README.md)：Ray分布式强化学习库，支持大规模强化学习训练
- [Gymnasium-Robotics](./gymnasium-robotics/README.md)：Farama Foundation开发的机器人强化学习环境库
- [LeIsaac](./leisaac/README.md)：使用 SO101Leader（[LeRobot](https://github.com/huggingface/lerobot)）提供遥操作功能，包括数据收集、数据转换和后续的策略训练

## 分类说明

| 分类                     | 核心特点        | 适用场景                |
| ---------------------- | ----------- | ------------------- |
| **Habitat Lab**        | 视觉导航与具身智能训练 | 视觉导航，具身AI研究         |
| **Isaac Lab**          | 机器人强化学习训练   | 人形机器人，多机器人系统        |
| **LeRobot**            | 机器人学习开源框架   | 多模态机器人学习，预训练模型      |
| **RLlib**              | 强化学习库       | 通用强化学习算法研究与大规模分布式训练 |
| **Gymnasium-Robotics** | 机器人仿真环境     | 机器人控制算法测试，抓取操作任务    |
| **LeIsaac**            | 遥操作机器人     | 机器人控制算法测试，抓取操作任务           |

