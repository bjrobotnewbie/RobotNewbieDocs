# DankDroneDownloader

一款用 C# 编写的 DJI 无人机自定义固件下载工具

## 项目链接

- GitHub: <https://github.com/cs2000/DankDroneDownloader>

## 项目介绍
本项目名为DankDroneDownloader（简称DDD），是一款用C#编写的DJI及部分Autel无人机自定义固件下载工具。针对DJI下架旧固件、限制用户自主刷机的现状，该工具可归档新旧版本固件，配合第三方刷机软件，支持将固件刷写到无人机、相机、遥控器等设备。
项目提供Windows桌面应用与网页版（支持Chrome、Firefox、Edge浏览器），推荐优先使用桌面版以获得完整功能。

## 主要特性
1.  支持大量DJI飞行器、FPV眼镜等设备的固件归档下载
2.  提供桌面端与网页端两种使用方式
3.  附带官方状态查询页面https://dddstatus.com 用于排查连接问题
4.  使用前需确保系统时间与NTP服务器同步，避免出现401未授权报错
