# polyanya

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/planning/motion-planning/polyanya/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 Polyanya 的路径规划

## 项目链接

- GitHub: <https://github.com/vleue/polyanya>

## 项目介绍
这是Rust语言实现的Polyanya路径规划算法项目，Polyanya是一种无妥协的导航网格任意角度路径规划算法。项目提供了WASM在线演示Demo，支持通过导航网格快速计算两点间最优路径。

## 主要特性
1.  基于Polyanya的高效任意角度路径规划，适配导航网格场景
2.  支持多层导航网格：
    - 可使用重叠网格实现3D多楼层/桥梁等场景导航
    - 支持单向通行图层
    - 可配置图层启用/禁用规则实现条件通行
    - 支持自定义图层通行成本，实现更真实的路径规划效果
