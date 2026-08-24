# Echo-Memory

Echo-Memory 官方代码：在条件化视频世界模型中研究记忆的控制性实验（上下文、压缩、空间、状态空间）。

## 项目链接

- GitHub: <https://github.com/Echo-Team-Joy-Future-Academy-JD/Echo-Memory>
- 项目主页: <https://echo-team-joy-future-academy-jd.github.io/Echo-Memory/>

## 项目概述

## 项目介绍
Echo-Memory 是京东未来学院Joy Future Academy的Echo团队推出的官方代码项目，对应论文《Echo-Memory: a controlled study of memory in action-conditioned video world models》，聚焦于研究动作条件视频世界模型中的记忆机制。
项目核心研究问题为：当生成场景需要离开后再返回时，哪种记忆类型可以帮助模型保留场景的身份、布局和视角，避免生成偏离原场景的内容。项目包含Wan视频主干网络、各类记忆模块、训练流程、数据工具、开放域回访资源以及评测套件，还提供了可复现的对照实验、消融脚本、回放与回访评估工具等。

## 主要特性
1.  支持Context、Compression、Spatial、State-Space四类记忆模块的对照研究
2.  提供完整的训练、推理与复现流程，包含动态SpatialVID数据集的训练脚本
3.  内置域内回访、开放域回访以及真值回放等多类评估方案
4.  配套提供预训练模型、测试数据集、在线演示Demo以及中英文开发者指南，支持快速上手使用。
