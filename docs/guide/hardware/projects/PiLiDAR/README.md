# PiLiDAR

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/hardware/projects/PiLiDAR/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

开源低成本 DIY 360°激光雷达扫描器与全景三维重建系统。

## 项目链接

- GitHub: <https://github.com/PiLiDAR/PiLiDAR>

## 项目介绍
PiLiDAR是一款开源低成本的DIY 360°激光雷达（LiDAR）扫描仪及全景3D重建系统，当前处于开发阶段，可基于树莓派硬件搭建，整体成本约200-280美元，适用于DIY 360°扫描与3D场景重建场景。

## 主要特性
- **LiDAR模块**：支持LDRobot LD06、LD19或STL27L激光雷达，具备CRC数据包完整性校验、基于曲线拟合校准的硬件PWM功能，可实现2D实时可视化及numpy/CSV格式导出。
- **全景模块**：可生成6K 360°球面图，通过Hugin拼接鱼眼照片，支持基于EXIF数据的恒定曝光、色彩增益迭代优化的恒定白平衡。
- **3D场景模块**：可基于角度与偏移量从2D平面组装3D场景，支持从全景采样顶点颜色，可通过Open3D以PCD/PLY/e57格式可视化导出，支持全局配准与ICP微调实现多场景对齐，还可进行泊松曲面网格化（树莓派4运行较慢，推荐在PC端执行）。
