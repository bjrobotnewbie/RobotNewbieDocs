# Multi-UAV-JEV

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/Multi-UAV-JEV/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于相机观测的无人机追逐任务，使用 MuJoCo 环境，结合 Jev 决策机制、RGB/深度 HUD 显示、重放与集集。

## 项目链接

- GitHub: <https://github.com/YongLD/Multi-UAV-JEV>

## 项目介绍
Multi-UAV-JEV 是基于 MuJoCo 仿真环境的多无人机协同追踪项目，核心为相机观测下的无人机追捕任务，采用 JEV 决策框架，支持 RGB/深度 HUD 显示、回放与 episode 数据采集，适配 Python 3.12，依赖 NeoHorse-Jev-4B 模型，遵循 Apache-2.0 协议。

## 主要特性
1. 支持 1/2/4 架无人机编队，各无人机具备独立关节、电机、相机感知、控制器与 JEV 决策模块，可实现追踪、前方封锁、预测拦截、支援等协同任务；
2. 共享相机观测数据，支持 RGB/深度可视化，观测信息可编辑，过期观测自动转为搜索模式；
3. 可自定义角色规则，运行时可加载有效配置；
4. 提供完整实时座舱界面，支持单无人机聚焦、动作概率/预测路径等信息查看，同步录制 20 FPS 全量数据。
