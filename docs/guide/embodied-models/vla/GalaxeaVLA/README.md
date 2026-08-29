# GalaxeaVLA

Galaxea 开源视觉 - 语言 - 动作控制（VLA）仓库

## 项目链接

- GitHub: <https://github.com/OpenGalaxea/GalaxeaVLA>

## 项目介绍
GalaxeaVLA是OpenGalaxea团队开源的G0.5视觉语言动作（VLA）模型项目，主打单自回归流实现机器人推理与动作生成。项目提供了预训练权重、多机器人部署与仿真评估代码，支持在R1 Lite、R1 Pro、SO-100/101等实体机器人以及DROID、LIBERO、RoboTwin 2.0等仿真环境中使用，相关论文已发布于arXiv。

## 主要特性
1.  采用单自回归流架构，实现高效的机器人推理与动作生成
2.  提供`g05-base`等多款预训练 checkpoint，覆盖基础部署、仿真微调等场景
3.  支持R1系列、SO-100/101等实体机器人零样本部署
4.  兼容DROID、LIBERO、RoboTwin 2.0等主流机器人仿真评估基准
5.  提供完整的微调脚本，可基于基础权重自定义适配机器人平台
