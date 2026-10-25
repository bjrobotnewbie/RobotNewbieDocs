# DeepLiDAR

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/multi-sensor-fusion/DeepLiDAR/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于稀疏激光雷达数据和单色图像的室外场景深度预测：深度表面法向引导（CVPR 2019）

## 项目链接

- GitHub: <https://github.com/JiaxiongQ/DeepLiDAR>

## 项目介绍
DeepLiDAR是CVPR 2019论文对应的PyTorch实现，核心功能是基于稀疏LiDAR数据与单张彩色图像，通过表面法线作为中间表示，构建端到端深度学习系统，生成户外道路场景的稠密深度图。项目提供了训练、评估所需的代码，以及基于CARLA生成的合成数据集和预训练模型。

## 主要特性
1. 以表面法线为中间表示，实现从稀疏LiDAR与单目图像到稠密深度的转换；
2. 适配户外道路场景，支持KITTI深度补全基准数据集与自定义合成数据集；
3. 提供完整的训练、评估流程，预训练模型可直接加载使用；
4. 依赖环境明确，基于Python 2.7与PyTorch 0.4.0+实现。
