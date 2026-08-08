# genesis-nyx

Genesis Nyx 是 Genesis World 的 GPU 加速路径追踪渲染器插件，用作高真实感相机传感器。

## 项目链接

- GitHub: <https://github.com/Genesis-Embodied-AI/genesis-nyx>
- 项目主页: https://genesis-embodied-ai.github.io/genesis-nyx/latest/

## 项目概述

Nyx 作为 Genesis World 的渲染插件接入仿真环境，以相机传感器形式提供路径追踪渲染能力。它支持 PBR 材质、HDRI 与解析光照、3D Gaussian Splat 资产、attached/multi-camera 设置、多环境渲染以及逐像素对象 picking，适合生成高质量视觉观测和合成数据。

该仓库主要包含文档和可运行示例，安装预编译 wheel 后即可通过 Python 脚本体验渲染插件。它面向需要在物理仿真中获得真实感视觉、训练视觉策略或生成多模态数据的 Genesis 用户，是 Genesis World 仿真栈中负责视觉真实性的重要组成部分。
