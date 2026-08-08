# pySLAM
- GitHub仓库: https://github.com/luigifreda/pyslam

## 项目概述
pySLAM是一个混合Python/C++实现的视觉SLAM管道，支持单目、立体和RGB-D相机。该项目提供了丰富的功能，包括多种经典和现代的局部特征提取器、多种闭环策略（如词袋模型、VLAD、全局描述符等）、体积重建模块、深度预测模型集成以及语义分割能力，能够提升场景理解效果。它在单个Python环境中集成了所有这些功能，同时支持g2o和GTSAM两种后端优化库，适用于视觉SLAM的研究和开发。