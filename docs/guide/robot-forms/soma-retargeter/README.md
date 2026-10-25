# soma-retargeter

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/robot-forms/soma-retargeter/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于牛顿和 NVIDIA Warp 构建的 SOMA BVH 到人形机器人动作重映射库

## 项目链接

- GitHub: <https://github.com/NVIDIA/soma-retargeter>

## 项目介绍
SOMA Retargeter是一款由NVIDIA开发的BVH到仿人机器人运动重定向库，基于Newton和NVIDIA Warp构建。它可以将SOMA骨骼BVH格式的人类运动数据转换为仿人机器人可用的关节动画，最终输出可用于机器人控制、仿真工具的CSV文件。

## 主要特性
1.  **核心功能**：读取SOMA骨骼BVH动画，将人类关节比例适配到目标机器人，逐帧求解逆运动学，稳定接触点并限制关节范围，最终输出机器人根姿态和驱动关节值的CSV文件。
2.  **配套资源**：内置5款机器人（Unitree G1、Unitree H2、Booster T1、Agibot X2Ultra、Agibot A3T3）的配置与模型资产，附带10组示例BVH运动及对应CSV结果，另有15组用于逆运动学权重优化的BVH运动数据。
3.  **使用模式**：支持交互式可视化查看、单运动重定向流程，同时支持无头批量转换批量转换文件夹内的运动文件，还提供自定义机器人配置、逆运动学权重调优工具。
4.  **注意事项**：当前处于活跃测试阶段，API和功能可能变更；生成的运动为运动学结果，硬件部署前需在仿真中验证安全性、可行性与控制器兼容性。
