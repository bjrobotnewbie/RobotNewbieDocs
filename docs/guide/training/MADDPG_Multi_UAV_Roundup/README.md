# MADDPG_Multi_UAV_Roundup

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/MADDPG_Multi_UAV_Roundup/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 MADDPG 的多无人机目标聚合

## 项目链接

- GitHub: <https://github.com/reinshift/MADDPG_Multi_UAV_Roundup>

## 项目介绍
本项目是基于MADDPG（多代理深度强化学习）实现的多UAV目标围捕任务，提供了完整的训练与评估流程。项目包含自定义的多UAV围捕仿真环境，支持通过训练好的智能体完成多无人机协同包围目标的任务，附带了可直接使用的预训练模型。

## 主要特性
1.  **核心依赖**：基于Python3.9.0、PyTorch2.4.0+cu124、Gym0.26.2等版本构建，低版本兼容性未做保证
2.  **代码结构**：复用了PhilTABOR的MADDPG基础实现，包含代理、经验回放池、算法核心、网络模型模块
3.  **功能模块**：提供完整训练主循环、独立评估渲染脚本，内置数学工具函数与自定义仿真环境
4.  **附带资源**：提供`tmp/maddpg/UAV_Round_up`目录下的可用预训练模型，可直接用于任务测试
5.  可扩展至多目标捕获场景，相关实现可参考关联项目。
