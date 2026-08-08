# roslibjs

- 项目链接：https://github.com/RobotWebTools/roslibjs
- 项目主页：https://robotwebtools.github.io/roslibjs

## 项目概述

roslibjs 是**标准的 ROS JavaScript 库**，是 Robot Web Tools 项目的一部分，让你可以在浏览器中通过 WebSocket 连接到 ROS。

通过 roslibjs，你可以创建基于网页的 ROS 可视化和交互界面，实现机器人的 Web 远程控制。

### 主要功能

- 连接到 ROS 网桥（rosbridge_suite）
- 发布和订阅 ROS 话题
- 调用 ROS 服务
- 获取和设置 ROS 参数
- 支持 TF 变换
- 兼容 JSON 消息格式

### 使用方式

- 可以直接使用 CDN 引用：`https://cdn.jsdelivr.net/npm/roslib@1/build/roslib.min.js`
- 也可以通过 npm 安装使用
- 支持浏览器环境和 Node.js 环境

### 工作流程

1. 在 ROS 系统中运行 `rosbridge_server`（WebSocket 服务，默认端口 9090）
2. 网页中使用 roslibjs 连接到 WebSocket
3. JavaScript 代码就可以与 ROS 系统交互

roslibjs 是机器人 Web 应用开发的基础库，被广泛用于创建基于浏览器的机器人监控、可视化和控制界面。
