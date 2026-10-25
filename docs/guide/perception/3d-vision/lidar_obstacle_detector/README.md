# lidar_obstacle_detector

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/lidar_obstacle_detector/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 ROS 1/ROS 2 的实时 3D LiDAR 障碍物检测、跟踪及轨迹预测：地面分割、聚类、2.5D 占用率，可选 GPU CenterPoint (TensorRT)。单 CPU 核心~10 ms/扫描。

## 项目链接

- GitHub: <https://github.com/SS47816/lidar_obstacle_detector>
- 项目主页: <https://github.com/SS47816/lidar_obstacle_detector#readme>

## 项目介绍
lidar_obstacle_detector是一款面向ROS 1/ROS 2的实时3D激光雷达障碍物感知工具，可实现障碍物检测、跟踪与轨迹预测，支持CPU原生运行或可选GPU加速，适用于自动驾驶等需要激光雷达环境感知的场景。

## 主要特性
- 运行高效：单CPU核心处理单帧激光雷达点云仅需约10ms，支持ROS 1 Noetic、ROS 2 Humble/Jazzy，基于C++17开发
- 无信息丢失：识别目标生成跟踪框，其余物体生成2.5D柱体，覆盖99%标注对象，柱体融合可减少闪烁
- 稳定跟踪：采用带GIoU关联的卡尔曼滤波跟踪，运动目标可输出3秒轨迹预测
- 可选GPU加速：集成NVIDIA CUDA-CenterPoint（TensorRT），多帧输入提升检测精度，在Argoverse 2数据集上召回率达0.91，nuScenes验证集达0.98
- 鲁棒地面分割：采用Patchwork++算法，支持MIT开源协议
