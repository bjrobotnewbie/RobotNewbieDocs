# php_parkour

[RSS 2026] 感知类人公园跑：通过运动匹配串联动态人类技能

## 项目链接

- GitHub: <https://github.com/amazon-far/php_parkour>
- 项目主页: <https://php-parkour.github.io/>

## 项目介绍
本项目为RSS 2026论文《Perceptive Humanoid Parkour: Chaining Dynamic Human Skills via Motion Matching》对应的开源实现，项目名称为php_parkour（简称PHP），核心功能是让人形机器人自主完成基于视觉的长时程障碍场地跑酷任务，通过运动匹配技术串联人类动态技能，实现机器人的复杂运动能力。

## 主要特性
1. 采用三步式框架实现机器人跑酷：离线通过运动匹配将重定向的人类基础技能组合为长时程轨迹；训练带特权状态和地形观测的RL专家模型跟踪轨迹；通过DAgger+RL将专家模型蒸馏为基于深度的多技能策略。
2. 提供完整的工作流支持：包含运动匹配、训练评估、仿真到仿真（sim2sim）部署三大模块，适配不同使用需求，支持在MuJoCo环境中运行导出的深度策略。
3. 提供预训练资源：包含示例数据集、验证过的学生策略ONNX模型，可快速在MuJoCo中运行演示，无需从零开始训练。
