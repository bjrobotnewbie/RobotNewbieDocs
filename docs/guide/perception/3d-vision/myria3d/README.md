# myria3d

Myria3D：基于深度学习的空中激光雷达高分辨率语义分割

## 项目链接

- GitHub: <https://github.com/IGNF/myria3d>
- 项目主页: <https://ignf.github.io/myria3d/>

## 项目介绍
Myria3D是一款基于深度学习的开源库，专注于大规模高密度航空LiDAR点云的多分类语义分割任务。它基于PyTorch构建，兼容PyTorch-Geometric标准数据格式，依托PyTorch-Lightning和Hydra实现灵活快速的深度学习实验迭代。
该库支持3D分割神经网络的训练、推理流程，可对大型未知点云进行分割，并支持基于全点云的单类别IoU评估，模型评估结果可靠。项目最初适配法国Lidar HD项目，可实现地面、植被、建筑等多类目标的语义分割。

## 主要特性
1.  聚焦航空LiDAR点云语义分割场景
2.  内置优化的数据处理与训练评估逻辑
3.  支持大规模点云推理与精准的单类别模型评估
4.  基于成熟的PyTorch生态工具链，实验迭代灵活高效
5.  原生适配公开的高密度航空LiDAR数据集标准标注类别
