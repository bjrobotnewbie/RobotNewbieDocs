# pointcloud

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/datasets/pointcloud/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

存储点云（激光雷达）数据的 PostgreSQL 扩展。

## 项目链接

- GitHub: <https://github.com/pgpointcloud/pointcloud>
- 项目主页: <https://pgpointcloud.github.io/pointcloud/>

## 项目介绍
这是一个PostgreSQL扩展插件，用于存储激光雷达（LIDAR）点云数据，支持Linux、FreeBSD、macOS、Windows多平台，当前最新版本为1.2.5，官方Docker镜像拉取量可观。官方文档地址为https://pgpointcloud.github.io/pointcloud/。

## 主要特性
1.  专为PostgreSQL设计，可直接在数据库中管理LIDAR点云数据
2.  支持多版本PostgreSQL与Ubuntu系统，可搭配PostGIS使用
3.  内置持续集成流程，自动完成扩展编译与单元测试，保障代码质量
