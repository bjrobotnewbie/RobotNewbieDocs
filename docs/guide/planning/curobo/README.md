# curobo

- 项目链接：https://github.com/NVlabs/curobo
- 项目主页：https://nvlabs.github.io/curobo

## 项目概述

cuRobo是**NVIDIA开发的CUDA加速机器人运动生成库**，基于PyTorch、CUDA和Warp构建。主要功能：

1. **支持多种任务**：正逆运动学、碰撞检测、轨迹优化、几何规划、GPU原生感知、全身运动生成
2. **可扩展**：从单臂机械臂扩展到高自由度人形机器人都能支持
3. **感知加速**：GPU原生ESDF感知，从深度图像生成稠密符号距离场，比现有方法快10倍
4. **动力学感知轨迹优化**：使用B样条表示， enforce 平滑性和力矩限制

cuRobo为机器人运动生成提供了全套GPU并行算法，能大幅加速运动规划计算，特别适合高自由度机器人。