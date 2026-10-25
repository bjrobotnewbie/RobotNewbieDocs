# OverlapTransformer

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/OverlapTransformer/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[RAL 与 ESI 高被引论文 🏆] OverlapTransformer：一种高效且具备方位角不变性的 LiDAR 基于位置识别 Transformer 网络

## 项目链接

- GitHub: <https://github.com/haomo-ai/OverlapTransformer>

## 项目介绍
OverlapTransformer是RAL & ESI高被引论文对应的开源项目，是基于LiDAR的位置识别与回环检测的轻量型Transformer网络，为原有OverlapNet的升级版本，可作为骨干网络无缝集成到各类基于范围图像的方案中，支持RGBD相机、不同型号LiDAR等多类输入，还衍生出序列增强版本SeqOT与多视图扩展版本CVTNet。

## 主要特性
1. 高效性：单帧推理速度快，Python实现低于4ms/帧，C++实现低于2ms/帧；
2. 鲁棒性：具备自然数学特性，对偏航角变化具有不变性，在LiDAR相似度估计任务中兼具速度与精度优势；
3. 扩展性：支持多类输入类型，可适配不同LiDAR、RGBD相机等设备，衍生版本可提升长期位置识别性能。
