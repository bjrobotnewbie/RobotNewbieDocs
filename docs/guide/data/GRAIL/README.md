# GRAIL

- 项目链接：https://github.com/NVlabs/GRAIL
- 项目主页：https://research.nvidia.com/labs/dair/grail/
论文链接：https://arxiv.org/pdf/2606.05160
数据集：https://huggingface.co/datasets/nvidia/PhysicalAI-Robotics-Locomanipulation-GRAIL

## 项目概述
GRAIL是一个全数字化的数据生成管道，用于生成人形机器人的运动和操作数据。其核心功能包括：
1. 结合3D资产、模拟器就绪场景、机器人比例角色和视频基础模型先验，合成四维的人类-物体交互（HOI）轨迹
2. 支持将生成的轨迹重定向到Unitree G1等机器人平台
3. 可训练用于拾取、全身操作、坐姿和地形穿越等任务的通用策略
4. 仅使用GRAIL生成的数据训练的以自我为中心的视觉策略，能够直接迁移到真实世界的物体拾取和爬楼梯任务
5. 提供完整的项目文档和在线演示，方便开发者快速上手

该项目为机器人领域的数据生成提供了高效的解决方案，减少了对真实世界数据的依赖，推动了人形机器人操作技术的发展。