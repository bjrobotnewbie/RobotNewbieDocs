# usgs-lidar

AWS Entwine Point Tiles USGS LiDAR 公开数据集 GitHub 仓库

## 项目链接

- GitHub: <https://github.com/hobuinc/usgs-lidar>
- 项目主页: <https://registry.opendata.aws/usgs-lidar/>

## 项目介绍
本项目是AWS公开数据集项目，将USGS 3DEP LiDAR点云数据处理为云友好、可流式加载、无损且易用的格式。
AWS上该数据集有两种形式：
1.  请求者付费存储桶`s3://usgs-lidar`，包含全密度LASzip格式瓦片
2.  公开访问存储桶`s3://usgs-lidar-public`，包含镜像的EPT格式资源
数据总规模超过10万亿个点，涵盖950+个独立资源，可通过PDAL、Potree等工具读取、处理和可视化。

## 主要特性
1.  采用EPT分层细节层次格式，支持万亿级点云的可扩展存储与访问
2.  支持流式加载与本地按需选取数据区域，可通过PDAL实现动态坐标 reprojection
3.  提供公开访问的云存储资源，同时保留原始全密度LASzip格式备份
4.  兼容PDAL、LASzip、Potree、Plasio.js等开源点云处理与可视化工具
