# brachiation

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/brachiation/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

通过简化模型模仿学习臂跃运动

## 项目链接

- GitHub: <https://github.com/brachiation-rl/brachiation>

## 项目介绍
本项目是SIGGRAPH 2022会议论文《Learning to Brachiate via Simplified Model Imitation》的官方代码库，基于Python和PyTorch开发，用于通过简化模型模仿学习实现臂行运动控制，支持在仿真环境中训练、测试和可视化臂行智能体。项目官网提供论文和演示资源。

## 主要特性
1.  **环境依赖**：支持Linux/macOS，要求Python>=3.8、PyTorch>=1.9.0，需自定义编译PyBullet环境
2.  **快速运行**：提供一键测试安装、可视化预训练模型的脚本，支持简化模型控制器和完整模型控制器两种模式，还支持完整模型规划功能
3.  **完整训练流程**：支持先训练简化模型并生成轨迹，再基于轨迹训练完整模型的端到端训练流程
4.  附带预训练模型和示例轨迹，可直接用于演示和二次开发。
