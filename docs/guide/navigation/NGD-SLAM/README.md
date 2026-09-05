# NGD-SLAM

[IROS 2025] NGD-SLAM: 面向无 GPU 实时动态 SLAM 的新方法

## 项目链接

- GitHub: <https://github.com/yuhaozhang7/NGD-SLAM>

## 项目介绍
NGD-SLAM是一款基于ORB-SLAM3框架开发的视觉SLAM系统，针对动态环境设计，已被IROS 2025收录。它无需GPU加速，可在普通笔记本CPU上实现实时运行且不损失跟踪精度。项目支持Ubuntu 20.04和22.04系统，配套提供了论文ArXiv链接、IEEE Xplore链接以及B站演示视频。

## 主要特性
1.  面向动态环境优化，可在无GPU的CPU环境下实时运行
2.  基于ORB-SLAM3框架开发，保留原有系统的核心优势
3.  集成YOLO-fastest模型实现动态物体检测，权重与配置已内置
4.  依赖Pangolin、OpenCV、Eigen3等开源库，相关依赖库均提供编译指引
5.  附带轨迹对齐所需的Python工具链，支持与真值轨迹对比评估
