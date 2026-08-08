# OmniContact_sim2sim

论文《OmniContact: Chaining Meta-Skills via Contact Flow for Generalizable Humanoid Loco-Manipulation》的官方实现

## 项目链接

- GitHub: <https://github.com/Ingrid789/OmniContact_sim2sim>
- 项目主页: https://omnicontact.github.io/

## 项目概述

## 项目介绍
本项目是论文《OmniContact: Chaining Meta-Skills via Contact Flow for Generalizable Humanoid Loco-Manipulation》的官方实现，是一个面向长时序人形机器人移动操作的接触流框架。项目包含CFgen和CFtrack两个核心模块，支持在MuJoCo中运行，提供了官方项目页面、arXiv论文、在线演示demo以及Hugging Face数据集，采用CC BY-NC-SA 4.0开源协议。

## 主要特性
1.  **核心模块**：CFgen可生成搬运、推送、滑动、重定位、踢动等基础技能以及链式组合元技能的任务空间接触流参考；CFtrack作为底层策略，可跟踪CFgen生成的参考或完整的.npz格式人机交互运动数据。
2.  **应用场景**：支持通用人形机器人的复杂多步骤移动操作任务，实现可泛化的技能串联。
3.  **配套资源**：提供预训练策略、数据集以及在线可视化演示工具。
