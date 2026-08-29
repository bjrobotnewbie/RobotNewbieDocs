# LAStools

用于激光雷达处理的高效工具

## 项目链接

- GitHub: <https://github.com/LAStools/LAStools>

## 项目介绍
LAStools是一套高效的LiDAR点云处理工具套装，依托LASlib和开源压缩库LASzip，支持处理ASPRS LAS 1.0-1.4格式、压缩LAZ格式以及Terrasolid BIN、ESRI Shapefile、ASCII等多种点云数据。整体代码采用轻量高效的C++编写，支持多核并行与脚本化批量处理。

项目分为开源、免费和闭源三部分：开源部分包含LASlib和LASzip，以及laszip、las2las、las2txt等十余款工具；免费工具包含可视化工具lasview和栅格压缩工具demzip；闭源工具则覆盖点云转DEM、提取等高线、分类建筑与植被等专业处理功能。

## 主要特性
1.  支持多种主流LiDAR数据格式，内置无损LAZ压缩解压能力
2.  轻量高效的C++实现，支持多核并行与脚本化批量处理
3.  覆盖格式转换、数据清洗、空间索引、可视化、专业测绘分析等全流程点云处理能力
4.  提供开源免费与商业闭源的分层工具套装，满足不同使用需求
