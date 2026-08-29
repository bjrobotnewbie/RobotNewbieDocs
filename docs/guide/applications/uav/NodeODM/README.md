# NodeODM

轻量级 REST API，用于访问空中图像处理引擎，如 ODM 或 MicMac。

## 项目链接

- GitHub: <https://github.com/OpenDroneMap/NodeODM>
- 项目主页: <https://github.com/OpenDroneMap/NodeODM/blob/master/docs/index.adoc>

## 项目介绍
NodeODM是一套用于调用ODM、MicMac等航空影像处理引擎的标准REST API规范，配套提供了基于NodeJS开发的高性能、可用于生产环境的参考实现。该API被CloudODM、PyODM等客户端使用，可实现航空影像的批量处理。推荐通过Docker快速部署，Linux、Windows、macOS均可通过对应命令启动服务。

## 主要特性
1.  提供标准化的航空影像处理REST API接口
2.  内置生产级别的NodeJS参考实现
3.  支持通过Docker快速部署，兼容64位及以上CPU架构
4.  可灵活对接ODM等多种航空影像处理引擎，支持自定义替换底层处理镜像
5.  同时支持Docker和Apptainer根less运行模式，适配HPC等特殊场景
