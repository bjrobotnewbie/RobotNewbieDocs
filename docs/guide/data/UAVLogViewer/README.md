# UAVLogViewer

无人机日志文件在线查看器

## 项目链接

- GitHub: <https://github.com/ArduPilot/UAVLogViewer>

## 项目介绍
UAVLogViewer是一款基于Javascript的无人机日志在线查看工具，支持解析Mavlink遥测日志和Dataflash日志，提供了在线演示站点。该工具可通过Docker快速部署，也支持本地编译运行，部署时需要配置Cesium ion令牌以使用地图功能。

## 主要特性
1.  支持解析Mavlink和Dataflight格式的UAV日志
2.  提供Docker一键部署方案，也支持本地编译运行
3.  支持静态文件部署到自有服务器
4.  内置热重载开发模式，方便二次开发调试
5.  附带完整的单元测试和端到端测试脚本
