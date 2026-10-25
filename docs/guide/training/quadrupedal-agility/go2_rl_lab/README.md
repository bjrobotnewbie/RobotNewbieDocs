# go2_rl_lab

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/quadrupedal-agility/go2_rl_lab/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[RSS 2026] 迈向基于混合专家（MoE）的稳健四足机器人从仿真到现实的可靠性预测。RSS 2026 官方实现。

## 项目链接

- GitHub: <https://github.com/wty-yy/go2_rl_lab>
- 项目主页: <https://robogauge.github.io/complete/>

## 项目介绍
本项目是RSS 2026论文《Toward Reliable Sim-to-Real Predictability for MoE-based Robust Quadrupedal Locomotion》的官方实现，基于unitree_rl_gym开发，用于通过强化学习（RL）训练宇树Unitree Go2四足机器人，支持Isaac Gym、Mujoco仿真环境及真实物理机器人部署。

## 主要特性
- 支持多种训练任务配置，含MoE相关变体（如go2_moe_cts为论文最终版本）
- 提供训练、恢复训练、模型评估功能，支持并行仿真环境、设备配置（CPU/GPU）
- 集成RoboGauge评估工具，可输出YAML格式结果并同步至TensorBoard
- 支持仿真到真实（Sim2Real）迁移，具备可靠的仿真-真实可预测性
