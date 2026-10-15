# piper-dual-arm-smolvla-towel-folding

SmolVLA（SmolVLM2-500M）在真实双 AgileX Piper 机器人臂上实现视觉 - 语言 - 动作控制——基于经过验证的 ACT 安全基础实现连续权威融合，将真实毛巾折叠动作压缩为一条 750 步的技能序列（状态=0）。完整演示课程已包含。

## 项目链接

- GitHub: <https://github.com/dk2472780158-ctrl/piper-dual-arm-smolvla-towel-folding>
- 中文文档: https://github.com/dk2472780158-ctrl/piper-dual-arm-smolvla-towel-folding/blob/main/README_zh-CN.md

## 项目介绍
本项目基于SmolVLA（SmolVLM2-500M）视觉语言动作模型，在两台AgileX Piper机械臂上实现了真实毛巾折叠任务。以经过验证的ACT控制器作为安全基底，SmolVLA可以持续对机械臂轨迹进行微调，实现无跳跃、无控制权丢失的连续操作，仅需一条命令即可运行完整的750步折叠流程。项目搭载三路摄像头视觉输入，支持实时30Hz控制，还附带完整的图文教程。

## 主要特性
1.  **真实机器人落地的VLA方案**：使用SmolVLA作为骨干模型，直接将三路相机画面和关节状态转换为关节动作
2.  **双策略融合控制**：以ACT控制器作为安全基底，SmolVLA持续微调轨迹，无需切换控制权
3.  **安全无跳跃操作**：控制权权重连续变化（范围0~0.9），无二进制切换，修正幅度和速率均有严格限制
4.  **一键部署**：执行`bash run_hybrid_towel_blend750.sh`即可重置机械臂并运行完整折叠流程
5.  适配真实变形物体操作，兼顾控制稳定性和视觉响应灵活性
