# plainmp

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/planning/motion-planning/plainmp/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

快速运动规划，适用于 articulated robot，通过适度的提前优化（C++ 核心与 Python 绑定）实现，中等规模问题耗时小于 1ms。

## 项目链接

- GitHub: <https://github.com/HiroIshida/plainmp>

## 项目介绍
plainmp是一款面向关节机器人的超快速运动规划库，采用C++核心+Python绑定的架构，核心目标是实现高效的运动规划，中等规模问题的规划耗时可小于1ms，是原scikit-motionplan和tinyfk项目的重写版本，实现了约100倍的速度提升。

## 主要特性
1. 快速采样运动规划，中等规模问题（如RRTConnect算法）规划耗时小于1ms
2. 支持碰撞感知的逆运动学（IK）求解器
3. 可适配多种机器人模型，包括移动基座、双臂、带物体附着的机器人等
4. 提供灵活框架，支持自定义机器人模型与运动规划问题
5. 支持基元（球体、长方体、圆柱体等）及点云与机器人的碰撞检测
6. 包含测试版功能：采样式约束运动规划（如人形机器人全身规划）、基于SQP的约束运动规划（可作为采样式规划器的平滑工具）
7. 依赖OMPL（含未合并的ERTConnect PR）、scikit-robot框架，采用BSD 3 License（cpp目录代码为MPL2.0），当前依赖球体近似机器人本体。
