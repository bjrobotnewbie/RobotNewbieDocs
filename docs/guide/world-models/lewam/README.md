# lewam

LeWAM: 端到端的世界与动作建模，基于 JEPAs

## 项目链接

- GitHub: <https://github.com/MinghaoFu/lewam>
- 项目主页: <https://le-wam.github.io/>

## 项目介绍
LeWAM（End-to-End World and Action Modeling with JEPAs）是基于JEPAs的端到端世界与动作建模项目，支持目标条件视觉规划、任务完成（行为克隆）两类任务，提供配套的代码、数据集与模型检查点，可用于机器人视觉规划、强化学习（RL）相关的仿真环境任务建模，支持MuJoCo仿真环境，适配CUDA加速。

## 主要特性
1. 核心技术：采用JEPAs框架实现世界与动作的端到端建模；
2. 任务支持：覆盖目标条件视觉规划（gr）、任务完成（tc，行为克隆）两类任务；
3. 配套资源：提供Hugging Face平台的仿真数据集、预训练检查点，支持快速部署；
4. 易用性：提供完整的安装、数据预处理、训练、评估流程脚本，支持自定义配置与参数覆盖，结果可自动存储。
