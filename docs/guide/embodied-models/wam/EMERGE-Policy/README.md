# EMERGE-Policy

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/EMERGE-Policy/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

EMERGE-Policy：机器人思维超越单一策略

## 项目链接

- GitHub: <https://github.com/EMERGE-Policy/EMERGE-Policy>
- 项目主页: <https://emerge-policy.github.io/EMERGE-Policy/>

## 项目介绍
EMERGE-Policy是一款机器人智能系统，核心目标是突破单一策略的局限，实现更灵活的机器人智能。该项目由多所高校联合开发，已发布v1.0.0版本，支持Web控制台与TUI交互界面，可管理机器人任务、切换场景、重置环境，还集成了Cosmos Policy WAM与OpenPI VLA版本，适配LIBERO、LIBERO-Plus等标准评估场景，支持ROS、SLAM、RL等技术框架，可用于机器人任务管理与智能决策相关场景。

## 主要特性
1. 提供Web控制台，支持浏览器端管理机器人任务，具备实时相机视图、对话交互、场景搜索、任务重置与切换功能，对话间场景与工作空间隔离，降低操作与实验组织成本。
2. 支持TUI界面的环境重置与场景切换，通过统一驱动生命周期接口适配新环境集成，更新BDDL配置并支持LIBERO评估。
3. 推出WAM版本，集成多模型服务器与多工作者批量推理，适配标准LIBERO、LIBERO-Plus评估场景。
