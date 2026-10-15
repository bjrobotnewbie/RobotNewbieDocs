# Batch-LIO

基于批次的点线激光：每~1ms 批次的 EKF 更新 + 批内去斜率，用于高带宽、低计算量的激光 - 惯性里程计（实现 Point-LIWO 创新#1 的复现）。

## 项目链接

- GitHub: <https://github.com/Functionhx/Batch-LIO>
- 中文文档: https://github.com/functionhx/batch-lio/blob/main/README.zh-CN.md

## 项目介绍
Batch-LIO是Point-LIO的批处理扩展版本，复刻了USTC本科论文《高带宽轮式激光惯性里程计》中的创新点#1，基于HKU-MARS的Point-LIO开发，兼容ROS 2 Humble与ROS 1 Noetic，仅支持CPU运行，暂不包含轮速输入功能。它通过将激光点云按~1ms时间窗口分组，实现单窗口单次EKF更新，并支持窗口内运动去畸变，可在更高数据带宽下降低计算量。

## 主要特性
1.  **批处理更新**：将激光点云分组为~1ms时间窗口，替代原Point-LIO按单时间戳更新的方式，每个窗口仅执行一次EKF更新
2.  **窗口内去畸变**：利用EKF估计的角速度和线速度，将窗口内所有点云补偿至窗口末尾时刻，完成运动去畸变
3.  **可选OpenMP加速**：为点云KNN匹配与平面拟合循环添加OpenMP并行加速，仅在批处理分组扩大后能体现性能提升
4.  支持通过ROS参数切换批处理模式，当`batch_dt ≤0`时行为与原Point-LIO完全一致，还可独立开关去畸变与并行加速功能。
