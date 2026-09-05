# geo-clip

这是我们在 NeurIPS 2023 论文 "GeoCLIP：基于 Clip 的地点与图像之间的对齐，以实现有效的全球定位" 的官方 PyTorch 实现。

## 项目链接

- GitHub: <https://github.com/VicenteVivan/geo-clip>
- 项目主页: <https://arxiv.org/abs/2309.16020>

## 项目介绍
GeoCLIP是NeurIPS 2023论文的官方PyTorch实现，是一款受CLIP启发的全球图像地理定位工具。它通过对比学习对齐图像与地理坐标，在Im2GPS3k、YFCC26k、GWS15k和Geo-Tagged NUS-Wide等基准数据集上取得了当前最优的地理定位效果。
该项目还提供了预训练的GPS编码器，可用于辅助其他地理感知神经网络模型，提升下游任务性能。

## 主要特性
1.  采用CLIP风格的对比训练方式，基于全球470万张图像的MP-16数据集学习不同地域的视觉特征
2.  支持全球图像地理定位推理，可以输入单张图像输出Top-K预测的经纬度坐标及置信度
3.  预训练的位置编码器可提取高质量GPS特征，辅助提升地理感知分类等下游任务效果
4.  提供pip快速安装方式，附带Colab在线演示demo，部署使用便捷。
