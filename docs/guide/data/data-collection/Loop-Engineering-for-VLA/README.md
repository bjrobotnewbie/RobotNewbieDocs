# Loop-Engineering-for-VLA

RGB/RGB-D LeRobot VLA 数据集的收集、合并、审计、可视化与发布工具包。

## 项目链接

- GitHub: <https://github.com/dsta022/Loop-Engineering-for-VLA>

## 项目介绍
本项目是面向LeRobot VLA的多模态数据集工具包，用于收集、合并、审核、可视化和发布RGB/RGB-D格式的机器人数据集。支持标准LeRobot生态的纯RGB数据集，以及带可选深度附属文件的RGB-D数据集，可将RGB视频与机器人动作、状态、元数据、深度数据统一处理。
工具包支持Orbbec RGB-D设备数据采集，可合并多个同结构LeRobot数据集，审核视频、动作、元数据质量并可选检查深度数据，基于审核后的片段生成清洗后的数据集，还可将最终数据集上传至Hugging Face。
此外工具包内置无框架依赖的数据采集模块，可直接连接机器人与相机，生成符合LeRobot v3.0格式的数据集，无需依赖lerobot框架。

## 主要特性
1.  支持纯RGB、RGB-D以及视觉触觉（开发中）三种数据采集模式
2.  提供数据集合并、质量审核、清洗导出、Hugging Face上传全流程工具
3.  内置独立无依赖的采集层，兼容Orbbec、Intel RealSense等设备
4.  遵循LeRobot标准数据集格式，可直接用于下游VLA、RL等机器人模型训练
