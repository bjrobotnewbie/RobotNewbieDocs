# microduck_rl

Microduck（mjlab）的强化学习训练环境

## 项目链接

- GitHub: <https://github.com/pollen-robotics/microduck_rl>
- 项目主页: <https://pollen-robotics.com/microduck>

## 项目介绍
本项目是面向重量约800g、高度约25cm的双足机器人Microduck的强化学习训练环境，基于mjlab（MuJoCo Warp）构建，使用PPO算法训练策略。项目包含完整的 sim2real 流程，支持 actuator 物理模拟、领域随机化、间隙仿真，训练得到的策略可导出为ONNX格式，部署到真实机器人上。训练速度为50Hz，可通过Hugging Face Jobs远程运行，无需本地GPU。

## 主要特性
1.  支持基于Microduck机器人的强化学习训练，提供标准行走等任务环境
2.  内置完整的sim2real工程化方案，包含物理建模、随机化、奖励设计等关键环节
3.  训练完成的策略可导出为ONNX格式，适配真实机器人部署
4.  支持通过uv快速配置环境，提供训练、可视化、导出、部署全流程命令行工具
5.  支持本地GPU训练，也可通过Hugging Face Jobs远程运行训练任务
