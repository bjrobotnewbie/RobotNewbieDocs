# lerobot-rgb-rgbd-vla-dataset-toolkit

用于收集、合并、审计、可视化和发布 RGB/RGB-D LeRobot VLA 数据集的工具集。

## 项目链接

- GitHub: <https://github.com/dsta022/lerobot-rgb-rgbd-vla-dataset-toolkit>

## 项目介绍
本项目是面向LeRobot的RGB/RGB-D视觉语言动作模型（VLA）数据集端到端工具包，可完成数据集采集、合并、审核、可视化、增强与发布全流程，实现从采集到优化的可追溯闭环。项目支持生成可直接用于训练的LeRobot格式数据集，已发布两个公开数据集：RGB-D格式的`DerekLX/lerobot_derek_depth`，以及包含2318个片段、249万帧的纯RGB格式数据集`dadm022/lerobot_rgb_vla`。

## 主要特性
1.  完整流程覆盖：支持采集、合并、审核、可视化、语言增强、策略迭代与Hugging Face上传全链路
2.  多模态适配：支持纯RGB采集，以及Orbbec/RealSense等RGB-D相机采集，还在开发视觉触觉采集功能
3.  可追溯性：所有数据集操作均可留痕审计
4.  内置工具链：包含本地数据预览、深度可视化、语义评估插件、策略迭代合约等辅助工具
5.  兼容LeRobot标准数据集格式，支持Python 3.12+环境。
