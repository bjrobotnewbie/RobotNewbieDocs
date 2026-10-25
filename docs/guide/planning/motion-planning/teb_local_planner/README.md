# teb_local_planner

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/planning/motion-planning/teb_local_planner/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 Timed-Elastic-Bands（ROS 包）构建的移动机器人最优轨迹规划器，考虑独特的拓扑结构

## 项目链接

- GitHub: <https://github.com/rst-tu-dortmund/teb_local_planner>
- 项目主页: <http://wiki.ros.org/teb_local_planner>

## 项目介绍
teb_local_planner是一款基于Timed-Elastic-Bands算法的ROS功能包，作为2D导航栈base_local_planner的插件，为移动机器人提供局部轨迹规划与优化能力，适用于仿真环境及真实机器人场景，支持类车机器人，可通过ROS Buildfarm的Melodic分支构建使用。

## 主要特性
- 基于Timed-Elastic-Bands算法，运行时优化机器人轨迹，兼顾执行时间、避障距离与运动学约束
- 支持不同拓扑结构的最优轨迹规划，可用于移动机器人的在线轨迹规划与优化
- 支持类车机器人，具备代价图转换功能
- 提供配套教程，可参考ROS Wiki获取使用说明
