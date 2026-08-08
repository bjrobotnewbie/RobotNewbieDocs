# SAGE-3D_Official

这是论文"Towards Physically Executable 3D Gaussian for Embodied Navigation"的官方仓库。

## 项目链接

- GitHub: <https://github.com/Galery23/SAGE-3D_Official>

## 项目概述

## 项目介绍
本项目是论文《Towards Physically Executable 3D Gaussian for Embodied Navigation》的官方代码仓库，提出了SAGE-3D范式，将3D Gaussian Splatting（3DGS）升级为可执行、语义与物理对齐的视觉语言导航（VLN）环境基础。现有VLN研究多遵循 sim-to-real 范式，仅用3DGS实现照片级渲染，但缺乏细粒度语义与物理可执行性。SAGE-3D通过两大核心组件解决该问题：对象级语义锚定与物理感知交互适配，并配套发布了多份开源数据集。

## 主要特性
1.  为3DGS添加细粒度对象级语义标注，实现语义对齐
2.  为3DGS嵌入碰撞体，提供物理交互接口，支持真实物理执行
3.  配套发布InteriorGS等多份开源数据集，包含1000个带对象级标注的室内3DGS场景等资源，支撑相关研究。
