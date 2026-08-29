# mavp2p

灵活高效的 Mavlink 路由器

## 项目链接

- GitHub: <https://github.com/bluenviron/mavp2p>

## 项目介绍
mavp2p是一款灵活高效的Mavlink代理/桥接/路由命令行工具，基于gomavlib库开发。主要用于将串口连接的无人机飞行控制器与地面站网络进行连接，也可搭建任意涉及串口、TCP、UDP的路由链路，实现不同物理层和传输层的通信。

## 主要特性
1.  支持连接任意数量的不同类型端点：串口、UDP（客户端/服务器/广播模式）、TCP（客户端/服务器模式）
2.  兼容Mavlink 1.0和2.0，支持所有Mavlink方言
3.  自动发送心跳包，可自动向Ardupilot设备请求数据流并拦截地面站的流请求
4.  支持按目标系统ID/组件ID路由消息，支持使用域名替代IP地址
5.  断线后自动重连TCP/UDP服务器，自动移除不活跃的TCP/UDP客户端
6.  可将遥测数据导出存储到磁盘，支持Linux、Windows多系统，arm6、arm7、amd64多架构，兼容Alpine等轻量发行版。
