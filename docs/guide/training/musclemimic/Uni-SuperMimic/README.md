# Uni-SuperMimic

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/musclemimic/Uni-SuperMimic/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

SuperMimic-UniLab：基于 UniLab 的独立重实现，用于全身人形运动跟踪。

## 项目链接

- GitHub: <https://github.com/Motphys/Uni-SuperMimic>

## 项目介绍
Uni-SuperMimic是SuperMimic在UniLab平台上的独立复现项目，核心用于Unitree G1人形机器人的全身运动跟踪，适配LAFAN1运动数据集，采用mjwarp、MuJoCo和Motrix作为后端，参考SuperMimic的`supermimic_vibed`实现，依赖PyPI的unilab库，相关研究成果已发布于arXiv论文《SuperMimic: Scaling Humanoid Whole-Body Control with One Differentiable World Model》。

## 主要特性
- 包含可微分世界模型、目标条件策略、基于Manager的任务框架
- 提供40种运动资产工具，支持训练入口与确定性全库评估
- 内置环境、策略、评估、渲染等模块，支持运动跟踪任务的快速部署与验证
