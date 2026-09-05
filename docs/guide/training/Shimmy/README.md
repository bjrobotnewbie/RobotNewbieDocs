# Shimmy

PettingZoo 和 Gymnasium 绑定：适用于 Farama 之外的流行强化学习环境

## 项目链接

- GitHub: <https://github.com/Farama-Foundation/Shimmy>
- 项目主页: <https://shimmy.farama.org>

## 项目介绍
Shimmy是一款API转换工具，为Farama之外的主流强化学习环境提供Gymnasium和PettingZoo兼容绑定，帮助开发者快速将第三方环境接入Farama的强化学习生态。项目提供官方文档站点与Discord开发协作社区，可通过PyPI快速安装。

## 主要特性
1.  **环境转换支持**：
    - 将OpenAI Gym环境转换为Gymnasium格式
    - 将DeepMind Control单智能体环境转换为Gymnasium格式
    - 将DeepMind Control Soccer多智能体环境转换为PettingZoo格式
    - 将OpenSpiel环境转换为PettingZoo格式
2.  **便捷安装**：支持通过PyPI一键安装，可按需安装对应环境的依赖包
3.  适配多Python版本，不同扩展包对应不同Python版本上限要求
