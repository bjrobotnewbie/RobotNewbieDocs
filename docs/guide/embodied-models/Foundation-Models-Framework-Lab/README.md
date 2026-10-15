# Foundation-Models-Framework-Lab

一个用于基于Apple Foundation Models框架构建、测试和评估应用的实践实验室。

## 项目链接

- GitHub: <https://github.com/rudrankriyam/Foundation-Models-Framework-Lab>

## 项目介绍
Foundation-Models-Framework-Lab 是一款原生iOS和macOS开发工作台，用于学习、测试和部署Apple Foundation Models框架。它将提示词、配置、工具、对话记录和运行证据统一管理，同时为需要专用接口的API提供针对性实验环境。
支持两种核心工作流：加载预设示例修改后快速运行，或自定义编写提示词与工具，完整追踪运行过程、对比适配器效果并导出可复现的实验数据。

## 主要特性
1.  三大核心功能模块：
    -  库：包含18个可编辑示例、14个引导实验、3个专题工作坊、保存的实验和专用工作区
    -  实验场：支持编辑提示词、配置模型与工具、流式响应、语音输入、保存实验并导出Swift代码
    -  运行记录：查看持久化的运行状态、配置、对话记录、工具调用、耗时和Token使用情况
2.  支持iOS 26.0+/macOS 26.0+，需Apple Silicon芯片运行本地模型，开启Apple Intelligence才能执行实时模型推理，兼容Xcode 26.6和Xcode 27。
