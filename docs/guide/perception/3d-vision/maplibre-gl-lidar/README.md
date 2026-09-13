# maplibre-gl-lidar

MapLibre 插件，用于可视化激光雷达点云

## 项目链接

- GitHub: <https://github.com/opengeos/maplibre-gl-lidar>
- 项目主页: <https://opengeos.org/maplibre-gl-lidar>

## 项目介绍
maplibre-gl-lidar是一款基于deck.gl的MapLibre GL JS插件，用于可视化LiDAR点云数据，支持加载LAS/LAZ/COPC、EPT格式的点云文件，可在Web端实现点云的三维展示与交互。项目提供在线预览工具，支持通过URL参数快速分享加载指定点云，兼容TypeScript，同时提供React、Vue框架集成方案。

## 主要特性
1.  支持加载LAS 1.0-1.4版本的LAS/LAZ/COPC文件，以及EPT服务流式加载超大数据集
2.  支持动态视口流式加载COPC点云，优化大数据集加载性能
3.  提供多种着色方案：高程、强度、分类标签、RGB原色
4.  自带交互式分类图例，可单独切换显示不同点云分类类型
5.  支持基于百分位的色彩映射，自动剔除异常值优化色彩分布
6.  提供交互式控制面板，支持点拾取查看详细属性、垂直偏移调整、高程范围过滤
7.  自动完成投影坐标到WGS84的转换，支持程序化API加载与样式配置
8.  内置deck.gl PointCloudLayer优化分块渲染，支持React、Vue框架集成
