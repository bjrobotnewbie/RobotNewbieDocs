# libcanard

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/hardware/embedded-systems/libcanard/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

C 语言中 Cyphal/CAN 协议的高完整性实时嵌入式系统紧凑实现

## 项目链接

- GitHub: <https://github.com/OpenCyphal/libcanard>
- 项目主页: <http://opencyphal.org>

## 项目介绍
libcanard是一款用C语言实现的Cyphal/CAN协议紧凑库，面向高完整性实时嵌入式系统，支持Cyphal v1.1、v1.0及旧版UAVCAN v0（即DroneCAN），适配Classic CAN与CAN FD，支持冗余/非冗余配置，可运行于8/16/32/64位平台，包括仅32K ROM和32K RAM的资源受限裸机MCU。它提供极简的平台适配接口，可快速移植到各类支持CAN的MCU，配套平台特定组件仓库可复用驱动、示例等资源，用于构建应用的媒体IO层。

## 主要特性
- 支持多版本Cyphal协议及旧版DroneCAN
- 兼容Classic CAN、CAN FD，支持冗余与非冗余配置
- 适配多架构平台，资源占用极低
- 平台接口简洁，可快速适配各类CAN MCU
- 提供可运行示例，便于快速上手
