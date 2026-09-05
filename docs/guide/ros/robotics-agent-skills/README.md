# robotics-agent-skills

使 AI 代码助手生成生产级机器人软件的关键技能：ROS1、ROS2、设计模式、SOLID 原则及测试——适用于 Claude Code、Cursor、Copilot 以及任何支持 SKILL.md 协议的智能体。

## 项目链接

- GitHub: <https://github.com/arpitg1304/robotics-agent-skills>

## 项目介绍
本项目是面向AI编码助手的工业级机器人开发知识库，可将`SKILL.md`格式的技能文件导入Claude Code、Cursor、Copilot等兼容的AI代理框架中，帮助AI生成符合工程规范的ROS1/ROS2软件。
它弥补了通用编码助手缺失的机器人工程细节，解决了QoS适配、确定性启动、安全关闭、可测试性等生产级机器人开发痛点。

## 主要特性
1.  支持生成符合规范的ROS1/ROS2代码，包含安全节点、正确QoS配置、生命周期模式、测试用例、启动文件、Docker配置等
2.  提供10+机器人开发技能包，涵盖ROS2开发、机器人感知、测试、部署、安全等场景
3.  内置对比验证案例，证明加载技能后AI生成的代码质量显著提升：包含完整生命周期节点、适配传感器的QoS配置、线程安全的传感器处理、完善的测试用例等
4.  提供一键安装脚本和手动导入两种部署方式，支持自定义选择技能包组合。
