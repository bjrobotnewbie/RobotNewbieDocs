# robo-boy

- 项目链接：https://github.com/tessel-la/robo-boy

## 项目概述

Robo-Boy 是一款专为移动设备设计的 ROS 2 机器人控制 Web 应用，灵感源自复古手持游戏机。它具有 React 前端，通过 rosbridge 进行 ROS 2 集成，使用 Caddy 和 HTTPS 进行安全的本地开发设置。

主要功能：
- 响应式设计，支持桌面和移动设备
- 通过 rosbridge 连接 ROS 2
- 显示相机流（通过 web_video_server）
- 用户可创建控制板，提供可重用的起始模板
- 支持 3D 可视化
- 行为树编辑，支持可搜索节点和 ROS 资源
- 可自定义主题，支持用户创建调色板

使用 Docker Compose 进行部署，本地开发使用 mkcert 设置 HTTPS，配置方便。
