# pizero_bikecomputer

基于 Raspberry Pi Zero (W, WH, 2 W) 或 Compute Module Zero 的开源自行车计算机，具备 GPS 和 ANT+ 功能，并提供离线地图与导航。

## 项目链接

- GitHub: <https://github.com/hishizuka/pizero_bikecomputer>
- 项目主页: <https://qiita.com/hishi/items/46619b271daaa9ad41b3>

## 项目概述

## 项目介绍
本项目是一款基于树莓派Zero（W、WH、2 W）或Compute Module Zero的开源自行车码表，支持GPS和ANT+功能，自带离线地图与导航能力。
它可以采集、记录并实时展示位置（GPS）、ANT+传感器（速度/踏频/功率）以及I2C传感器（气压/温度/加速度计等）的数据，还能生成`.fit`格式的骑行日志。当前已具备自行车码表的基础功能，后续还将拓展现有产品未有的新特性。官方硬件正在设计原型中，将以CERN-OHL-S-2.0协议开源设计文件。

## 主要特性
1.  支持GPS与ANT+传感器数据采集、展示与记录
2.  内置离线地图与导航功能
3.  支持I2C外接传感器扩展
4.  支持导出`.fit`格式骑行日志
5.  支持一键安装部署，适配最新Raspberry Pi OS Trixie系统
6.  正在开发双屏显示与官方定制硬件
