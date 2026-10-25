# tiny-differentiable-simulator

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/tiny-differentiable-simulator/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Tiny Differentiable Simulator 是一个无需依赖的 C++ 和 CUDA 物理库，专为强化学习和机器人学设计，采用头文件编写。

## 项目链接

- GitHub: <https://github.com/erwincoumans/tiny-differentiable-simulator>

## 项目介绍
tiny-differentiable-simulator是一款无依赖的仅头文件形式的C++（支持CUDA）物理库，原项目从google-research迁移至Erwin Coumans的仓库，主要面向强化学习与机器人学领域。

## 主要特性
1. 实现多种刚体动力学算法，含正逆动力学，以及基于脉冲级LCP的接触模型、基于力的非线性弹簧阻尼器，还集成电机、伺服、SEA等执行器动力学模型；
2. 代码采用模板化设计，支持前向/反向模式自动微分标量类型（如CppAD、Stan Math fvar、ceres::Jet），也可使用常规float/double精度值，或内置定点整数数学实现跨平台确定性计算；
3. 可在单张RTX 2080 CUDA GPU上并行运行数千次模拟，帧率达50fps，还提供多种可视化工具。
