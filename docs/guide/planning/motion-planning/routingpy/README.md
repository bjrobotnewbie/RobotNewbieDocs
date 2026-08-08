# routingpy

🌎 这是一个 Python 库，用于以统一的方式访问所有公开的路由、等时线和矩阵 API。

## 项目链接

- GitHub: <https://github.com/routingpy/routingpy>
- 项目主页: <https://routingpy.readthedocs.io/en/latest/?badge=latest>

## 项目概述

## 项目介绍
routingpy是一款Python 3第三方库，旨在以统一的接口调用各类公开的路径规划、等时圈、距离时间矩阵类Web服务。它参考geopy的设计思路，帮助开发者便捷访问主流空间路由服务，无需适配不同服务商的差异化API，可用于获取步行、骑行、汽车、重型货车等多种出行方式的路线、计算可达区域以及生成N×M规模的距离时间矩阵。

目前支持的服务商包括Mapbox、OSRM、Openrouteservice、Google Maps、Graphhopper、OpenTripPlannerV2、本地Valhalla、本地OSRM以及IGN，后续还将持续新增支持的服务。该库已通过CPython 3.9~3.14以及PyPy3 3.9/3.10版本的测试，遵循Apache 2.0开源协议。

## 主要特性
1.  统一API接口：抹平不同路由服务商的调用差异，简化开发流程
2.  多服务支持：覆盖多款主流商用、开源路由服务
3.  多场景适配：支持路线规划、等时圈计算、距离矩阵生成三类核心空间计算需求
4.  多Python版本兼容：适配多个稳定版CPython和PyPy运行环境
