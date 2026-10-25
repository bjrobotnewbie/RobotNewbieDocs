# ACMMM25-UAV_ON

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/benchmark_data/ACMMM25-UAV_ON/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

## 项目链接

- GitHub: <https://github.com/iLearn-Lab/ACMMM25-UAV_ON>

## 项目介绍
本项目为ACMMM25-UAV_ON，全称UAV-ON: A Benchmark for Open-World Object Goal Navigation with Aerial Agents，是面向空中智能体的开放世界物体目标导航基准测试集，用于支撑相关算法的开发与评估。

## 主要特性
1. 包含14个UAV-ON 1.0环境，其中4个环境存在问题（CityPark和BrushifyRoad的AirSim深度输出异常、Slum环境打包后雾度过高、DownTown部分建筑表面深度数据不可靠），推荐使用剩余10个环境进行开发与评估；
2. 存在已知问题：部分测试场景中无人机初始生成位置过近障碍物，可通过增加z轴高度调整初始位置缓解；
3. 计划于2026年12月发布UAV-ON 2.0版本，修复现有环境存在的问题。
