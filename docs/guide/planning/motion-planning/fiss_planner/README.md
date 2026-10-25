# fiss_planner

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/planning/motion-planning/fiss_planner/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[RA-L 2022] FISS: 一种基于快速迭代搜索和采样策略的自动驾驶轨迹规划框架

## 项目链接

- GitHub: <https://github.com/SS47816/fiss_planner>

## 项目介绍
本项目是2022年RA-L收录的FISS轨迹规划框架，基于frenet_optimal_planner框架改进，面向自动驾驶场景，核心是通过快速迭代搜索与采样策略生成最优轨迹。该项目已停止维护，当前维护版本整合至frenet_planner仓库，支持ROS 1/2、Lanelet2、CommonRoad、CARLA等工具，可通过`planner.type: fiss`选择使用。

## 主要特性
1. 采用历史规划结果作为启发式先验信息，结合迭代搜索-生成-评估策略，减少高计算量操作，规划速度较现有框架提升2-6倍；
2. 原仓库版本可通过`paper-ral2022`标签获取论文对应代码，另有改进版本FISS+单独开源；
3. 依赖ROS、C++等技术，支持Ubuntu系统，可开箱使用。
