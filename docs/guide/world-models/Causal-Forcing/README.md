# Causal-Forcing

[ICML 2026] "Causal Forcing: 正确实现自回归扩散蒸馏的高品质实时交互式视频生成" 及 "Causal Forcing++" 官方代码库

## 项目链接

- GitHub: <https://github.com/thu-ml/Causal-Forcing>
- 项目主页: <https://thu-ml.github.io/CausalForcing.github.io/>

## 项目介绍
Causal Forcing系列是ICML 2026相关论文的官方代码库，包含Causal Forcing和Causal Forcing++两个方案，用于高质量实时交互式视频生成。该方案通过Causal ODE或Causal Consistency Distillation驱动非对称DMD，为实时交互式视频生成提供理论正确的初始化。项目支持文本到视频（T2V）和图像到视频（I2V）任务，还支持长视频生成扩展。

## 主要特性
1.  **Causal Forcing**：在视觉质量和运动动态上均优于Self Forcing，且保持相同训练成本和推理效率，支持分块和逐帧模型，逐帧模型可原生统一T2V和I2V任务。
2.  **Causal Forcing++**：用因果一致性蒸馏替代因果ODE，无需ODE数据整理，性能进一步提升，推出了首个1步/2步逐帧模型。
3.  提供完整训练流程、快速部署方案、长视频生成工具，附带预训练模型和官方文档。
