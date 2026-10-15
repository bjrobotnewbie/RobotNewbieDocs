# RadixQuantVLA

RadixQuantVLA 是一个统一且乐高式的框架，用于后训练量化、基准测试及 Vision-Language-Action（视觉 - 语言 - 动作）模型部署前的准备，集成了 QuantVLA、Omega-QVLA、OpenVLA、UniVLA、StarVLA、GR00T 和 Pi0.5 等多种路线，并配有标准启动器，在 LIBERO 基准测试上进行验证。

## 项目链接

- GitHub: <https://github.com/RadixRootMind/RadixQuantVLA>
- 中文文档: https://github.com/radixrootmind/radixquantvla/blob/main/docs/zh_cn/README.md

## 项目介绍
RadixQuantVLA是一个面向视觉-语言-动作（VLA）模型的统一框架，用于模型的后训练量化、LIBERO基准测试及部署准备，整合了QuantVLA、Omega-QVLA、OpenVLA、UniVLA、StarVLA、GR00T、Pi0.5等多条技术路线，通过标准化启动器、检查点约定与输出格式，实现不同VLA模型及量化方法的统一管理与验证，支持A100-40GB硬件，适配DCU、NPU部署场景。

## 主要特性
1. 采用乐高式模块化设计，整合多类VLA模型与量化方法，支持W4A8、W4A4、GPTQ、QVLA等多种量化策略；
2. 提供标准化启动器与验证流程，基于LIBERO基准完成量化模型的功能验证；
3. 支持模型的量化、基准测试与部署准备全流程，适配不同硬件部署需求。
