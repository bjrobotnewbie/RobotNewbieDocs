# 机器人导航

机器人导航是指机器人在环境中自主移动并完成任务的技术，是移动机器人的核心能力之一。本章节涵盖机器人导航的核心技术与主流方法。

## 导航技术分类说明

| 分类 | 核心内容 | 典型技术 |
|------|---------|---------|
| **SLAM 技术** | 同时定位与建图 | SLAM Handbook, 视觉SLAM十四讲 |
| **导航数据集** | 用于训练和评估导航算法的基准数据 | Matterport3D |

> **注意**：视觉语言导航 (VLN) 模型已归类到 [基础模型](/guide/embodied-models/vln/README.md) 目录下，因为它们属于端到端的 AI 模型架构，而非传统的导航技术栈。

## 项目列表

### SLAM 技术

- [SLAM 手册](/guide/navigation/slam-handbook/README.md)
- [SLAM 十四讲](/guide/navigation/slambook2/README.md)

### 导航数据集

- [Matterport3D](/guide/navigation/Matterport3D/README.md)

## 与其他分类的区别

| 目录 | 定位 | 核心特点 |
|------|------|---------|
| **navigation/** | 传统导航技术栈 | SLAM、定位、建图、经典路径规划算法 |
| **embodied-models/vln/** | AI 导航模型 | 端到端、多模态融合、语言驱动的导航 |
| **planning/path-planning/** | 路径规划算法 | A*, RRT*, Dijkstra 等几何寻路算法 |
