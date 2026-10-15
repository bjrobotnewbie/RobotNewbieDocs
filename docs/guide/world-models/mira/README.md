# mira

MIRA 代码：具有表示自编码器（Representation Autoencoders）的多玩家交互式世界模型

## 项目链接

- GitHub: <https://github.com/mira-wm/mira>
- 项目主页: <https://mira-wm.com/>

## 项目介绍
MIRA是一款针对《火箭联盟》的实时多人交互式世界模型，由General Intuition、Kyutai和Epic Games联合研发。它基于50亿参数的潜在扩散模型，可根据四名玩家的操作实时生成游戏画面，单GPU即可实现20FPS的2v2对局模拟。项目提供了在线演示站点，同时附带了配套的技术报告和开源数据集。

## 主要特性
1.  **实时多人模拟**：支持完整2v2对局的模型内复现，帧率可达20FPS
2.  **基于表征自编码器的世界模型**：通过玩家操作生成同步的多视角游戏画面
3.  配套开源工具链：提供一键环境搭建脚本，依赖NVIDIA GPU，需通过pixi进行安装
4.  公开数据集：包含4秒时长的2v2对局数据，涵盖多视角画面、玩家操作和完整游戏状态数据，可通过HuggingFace Hub获取
