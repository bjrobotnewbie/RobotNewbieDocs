# segment-lidar

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/perception/3d-vision/segment-lidar/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Meta AI 提供的 Python 包，用于利用 Segment-Anything Model (SAM) 对 LiDAR 数据进行分割。

## 项目链接

- GitHub: <https://github.com/Yarroudh/segment-lidar>
- 项目主页: <https://yarroudh.github.io/segment-lidar/>

## 项目介绍
segment-lidar是一个Python包，用于对航空LiDAR数据进行实例分割，基于Meta AI的Segment Anything Model 3（SAM 3）实现。它将3D点云投影为图像，通过SAM 3识别目标对象后，将实例标签映射回原始点云，支持本地运行推理（需下载模型文件），适用于航空LiDAR点云的实例分割任务。

## 主要特性
1. 支持自动掩码生成、文本提示、框提示等交互方式
2. 支持顶视图、针孔相机等视角设置，可处理保存的标签栅格
3. 可选地面滤波功能，支持输出LAS/LAZ格式文件
4. 基于Hugging Face的facebook/sam3模型，需配置HF_TOKEN访问
5. 推荐使用CUDA GPU加速SAM 3推理，兼容Python 3.10及以上版本
