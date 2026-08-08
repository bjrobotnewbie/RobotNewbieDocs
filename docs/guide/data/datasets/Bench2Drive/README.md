# Bench2Drive

- 项目链接：https://github.com/Thinklab-SJTU/Bench2Drive
- 项目主页：https://thinklab-sjtu.github.io/Bench2Drive/

## 项目概述

Bench2Drive是NeurIPS 2024数据集与基准跟踪论文提出的**基于世界模型强化学习的闭环端到端自动驾驶基准增强项目**。该项目针对端到端自动驾驶系统提供了综合评估基准，主要特点包括：

1. **系统性评估框架**：针对基于世界模型的强化学习方法在自动驾驶场景中的闭环性能提供标准化评估
2. **多扩展子项目**：衍生出多个专项评估方向：
   - Bench2Drive-Robust：评估真实部署问题如相机流故障、自状态估计误差和计算控制延迟
   - Bench2Drive-Speed：评估自动驾驶系统的速度定制功能
   - Bench2Drive-VL：支持VLM的闭环QA评估，解决Python版本兼容性问题
3. **完整数据集**：提供HuggingFace托管的Bench2Drive数据集，支持多样化的模型训练和验证
4. **活跃维护**：持续更新扩展功能，修复问题，社区讨论活跃

该项目为端到端自动驾驶研究提供了公平、全面的基准测试平台，促进了世界模型在自动驾驶领域的研究发展。