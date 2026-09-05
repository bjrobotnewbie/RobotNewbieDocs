# QGISFMV

QGIS 全运动视频 (FMV)

## 项目链接

- GitHub: <https://github.com/All4Gis/QGISFMV>
- 项目主页: <https://all4gis.github.io/QGISFMV/>

## 项目介绍
QGIS FMV是一款QGIS插件，可将全动态视频（FMV）集成到GIS工作流中。它支持播放MISB格式视频，在地图上展示遥测数据，可处理视频文件、流数据以及DJI无人机遥测数据，通过pymisb库解析MISB/KLV元数据，实现视频与地理空间图层的同步播放。

## 主要特性
1.  **实时地理符号化**：同步更新平台、 footprint、传感器波束、轨迹、帧中心等图层
2.  **MISB/KLV元数据支持**：通过pymisb解析元数据，支持导出CSV/PDF、生成ffprobe信息和码率图表
3.  **视频播放功能**：基于OpenCV解码，支持拖拽进度、循环播放、剪辑录制和帧导出
4.  **25+实时滤镜**：包含CLAHE、锐化、植被指数、去雾等多种图像处理工具
5.  **AI检测工具**：内置适配FMV/UAV场景的YOLO目标检测和智能CV分析能力
6.  **多路复用工具**：可将DJI视频与遥测数据打包为STANAG 4609格式的MISB .ts文件
7.  **流视频支持**：可打开UDP、TCP、RTP、RTSP格式的视频流
8.  配套实用工具：包含HUD、小地图、告警、地理围栏、书签和任务打包功能

该插件适配QGIS 4.x版本，采用GPL-3.0开源协议。
