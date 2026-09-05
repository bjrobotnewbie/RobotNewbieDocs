# scribblekitti

Scribble-Supervised LiDAR Semantic Segmentation, CVPR 2022 (口头)

## 项目链接

- GitHub: <https://github.com/ouenal/scribblekitti>
- 项目主页: <https://ouenal.github.io/scribblekitti/>

## 项目介绍
本项目是CVPR 2022 Oral论文《Scribble-Supervised LiDAR Semantic Segmentation》的代码与数据集发布仓库。针对LiDAR点云密集标注成本高、耗时长的问题，提出使用涂鸦标注（scribbles）作为弱监督信号，并发布首个LiDAR语义分割涂鸦标注数据集ScribbleKITTI，同时提供配套的训练 pipeline，可配合任意LiDAR语义分割模型使用，仅使用8%的标注点即可达到全监督性能的95.7%。

ScribbleKITTI基于SemanticKITTI训练集构建，包含10个序列共19130帧点云，仅标注了总点数的8.06%，保留了原数据集的19个分类，可兼容现有SemanticKITTI数据加载流程。

## 主要特性
1.  发布首个LiDAR语义分割涂鸦标注数据集ScribbleKITTI
2.  提出可适配任意LiDAR语义分割模型的弱监督训练 pipeline
3.  仅需少量涂鸦标注即可逼近全监督模型性能
4.  兼容现有SemanticKITTI数据加载与训练框架
