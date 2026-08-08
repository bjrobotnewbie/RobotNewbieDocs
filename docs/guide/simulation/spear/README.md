# spear

- 项目链接：https://github.com/spear-sim/spear

## 项目概述

SPEAR 是一个用于照片级真实感具身 AI 研究的仿真器。它是一个 Python 库，可以通过模块化插件架构连接并以编程方式控制任何 Unreal Engine 应用程序。

SPEAR 向 Python 公开了超过 14K 个独特的 UE 函数，相比现有的基于 UE 的仿真器，可编程功能增加了一个数量级。此外，单个 SPEAR 实例能够以 56 FPS 的速度将 1920x1080 照片级真实感图像直接渲染到用户的 NumPy 数组中，比现有的 UE 插件快一个数量级，同时还提供现有任何基于 UE 的仿真器都没有的真值图像模态（例如非漫反射本征图像分解、材质 ID 等）。

该项目通过在多个 Epic Games 示例项目中控制 6 个不同的具身智能体（每个具有不同的动作空间）展示了其灵活性，包括：CitySample 中的人和汽车、StackOBot 中的飞行机器人、CropoutSample 中的多个智能体、GameAnimationSample 中的跑酷人物和四足机器人。
