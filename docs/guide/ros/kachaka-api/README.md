# kachaka-api

智能家具平台「Kachaka」API

## 项目链接

- GitHub: <https://github.com/pf-robotics/kachaka-api>
- 项目主页: <https://kachaka.zendesk.com/hc/ja/articles/7660222791183-%E3%82%AB%E3%83%81%E3%83%A3%E3%82%ABAPI>

## 项目概述

## 项目介绍
本项目是智能家具平台「カチャカ」的官方API仓库，提供控制该设备移动、对接，以及获取设备状态和传感器数据的功能。支持本地网络设备或设备内置的Playground用户环境访问，官方提供Python和ROS 2的SDK，同时基于gRPC通信接口，也支持其他语言调用。使用前需通过手机APP开启API权限，并可通过设备IP或`kachaka-<序列号>.local`域名访问。

## 主要特性
1.  提供设备移动、对接控制与状态、传感器数据获取能力
2.  官方支持Python 3.10+、ROS 2 Humble(Ubuntu 22.04 LTS)开发套件
3.  兼容gRPC标准，可通过其他编程语言直接调用
4.  支持本地网络与设备内置Playground两种运行环境
5.  提供多场景使用文档，包含快速体验、Python/ROS 2开发、跨语言调用等指南
