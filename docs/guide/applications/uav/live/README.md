# live

一个开源无人机表演与无人机蜂群地面控制站GUI前端

## 项目链接

- GitHub: <https://github.com/skybrush-io/live>
- 项目主页: https://skybrush.io

## 项目概述

## 项目介绍
Skybrush Live是Skybrush服务器的官方桌面端与网页端前端控制台，专为无人机表演、无人机集群设计的地面站GUI工具，用于管控集群无人机演出。

## 主要特性
1.  支持网页端与桌面端两种运行方式
2.  可对接Bing Maps、Mapbox、Mapzen地图服务（可选配置API密钥）
3.  基于Node.js与npm构建，支持Linux、Windows系统部署
4.  遵循GPLv3开源协议，可自由修改与分发

### 快速启动流程
1.  安装Node.js 20.x及npm包管理器
2.  克隆仓库后执行`npm install`安装依赖
3.  复制`.env.example`为`.env`并配置地图API密钥（可选）
4.  执行`npm start`启动网页版，或`npm run start:electron`启动桌面客户端，访问本地端口即可使用。
