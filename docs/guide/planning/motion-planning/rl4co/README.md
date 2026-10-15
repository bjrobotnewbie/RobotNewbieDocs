# rl4co

一个用于组合优化（CO）所有强化学习（RL）的 PyTorch 库

## 项目链接

- GitHub: <https://github.com/ai4co/rl4co>
- 项目主页: <https://rl4co.ai4co.org>

## 项目介绍
rl4co是一个基于PyTorch的组合优化强化学习（RL for CO, CO）工具库，旨在为基于RL的组合优化算法提供统一框架，推动该领域可复现研究，将科研与工程开发解耦。它依托TorchRL、TensorDict和PyTorch Lightning构建，支持快速搭建和测试RL组合优化方案。

## 主要特性
1.  集成了主流的RL组合优化算法与基准测试环境
2.  基于Hydra进行配置管理，支持灵活的实验参数调整
3.  遵循black代码规范，保证代码风格统一
4.  提供Colab快速上手示例，支持快速部署测试
5.  附带完整文档与社区支持，通过Slack进行交流协作，采用MIT开源协议
6.  内置完善的测试与代码覆盖率保障，支持高性能GPU并行训练
