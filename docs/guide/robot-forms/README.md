# 机器人形态分类

机器人形态分类用于描述**单个机器人本体长什么样、靠什么结构运动或操作**。本章节按"运动方式 + 物理结构类型"组织内容，避免把应用场景、协同方式或算法模块混入形态分类。

## 分类体系

| 分类 | 分类依据 | 典型对象 |
|------|---------|---------|
| [操作机器人](./manipulators/README) | 固定或半固定基座上的末端操作 | 串联机械臂、协作机械臂、SCARA、并联机器人 |
| [地面移动机器人](./ground-mobile-robots/README) | 陆地环境自主移动 | 轮式AGV、四足机器人、履带机器人 |
| [空中机器人](./aerial-robots/README) | 三维空间飞行 | 多旋翼无人机、固定翼无人机、扑翼机器人 |
| [水下机器人](./underwater-robots/README) | 水下环境运动与作业 | ROV、AUV、仿生鱼机器人 |
| [移动操作机器人](./mobile-manipulators/README) | 移动能力 + 操作能力 | 人形机器人、轮式/足式移动操作机器人 |
| [特殊移动机器人](./special-mobile-robots/README) | 非常规运动方式 | 爬壁机器人、蛇形机器人、球型机器人 |
| [软体机器人](./soft-robots/README) | 软材料和连续大变形 | 气动软体机器人、介电弹性体、形状记忆合金机器人 |
| [连续体机器人](./continuum-robots/README) | 连续弯曲、超冗余自由度 | 腱驱动连续体、同心管机器人、象鼻型机器人 |
| [可重构机器人](./reconfigurable-robots/README) | 模块重组、构型变化 | 模块化机器人、自重构机器人 |
| [微纳米机器人](./micro-nano-robots/README) | 微纳尺度、场驱动/化学驱动 | 磁控微型机器人、纳米马达、生物杂化微机器人 |
| [外骨骼机器人](./exoskeleton/README) | 可穿戴、人机耦合 | 康复外骨骼、工业助力外骨骼、军用动力外骨骼 |

## 相关章节

- [多机器人系统](/guide/multi-robot-systems/README)：多个机器人如何协同、编队、分工和通信。
- [应用场景](/guide/applications/README)：机器人系统在行业和任务中的落地应用。

- [awesome-robot-descriptions（精选优秀机器人描述文件（URDF、MJC…）](/guide/robot-forms/awesome-robot-descriptions/README)

- [phobos（Blender的一个插件，支持在所见即所…）](/guide/robot-forms/phobos/README)

- [robot_retargeter（从SMPL-X/源机器人到目标人形机器人…）](/guide/robot-forms/robot_retargeter/README)

- [gmr-motionlab（一个用于人形运动重定向、pkl运动可视化…）](/guide/robot-forms/gmr-motionlab/README)

- [humanoid-motion-intelligence（人形机器人运动智能论文、开源项目、产业与…）](/guide/robot-forms/humanoid-motion-intelligence/README)
