# ImageWAM

ImageWAM: 世界动作模型是否真的需要视频生成，还是只需要图像编辑？

## 项目链接

- GitHub: <https://github.com/yuyangalin/ImageWAM>

## 项目介绍
ImageWAM是一类基于图像编辑基础模型构建的世界动作模型，为官方PyTorch实现项目。本仓库包含在LIBERO、LIBERO-plus和RoboTwin数据集上进行论文实验所需的训练与评估代码。项目主推基于FLUX.2构建的FLUX.2 ImageWAM，提供4B和9B两种参数量版本，性能为系列中最强；同时还支持OmniGen2 ImageWAM和Ovis-U1 ImageWAM，其中Ovis-U1仅搭载1.1B的DiT图像编辑模块，参数量最小，在多数场景下可媲美更大尺寸的模型。

## 主要特性
1.  基于成熟图像编辑基础模型构建世界动作模型，无需依赖视频生成流程
2.  提供多参数量版本适配不同部署需求，覆盖从移动端到高性能场景
3.  在RoboTwin 2.0机器人基准测试中排名前五，在LIBERO等机器人学习数据集上表现优异
4.  完整开源训练与评估代码，附带预训练模型与项目演示页面
