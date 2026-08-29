# vleue_navigator

基于 NavMesh 的路径规划

## 项目链接

- GitHub: <https://github.com/vleue/vleue_navigator>
- 项目主页: <https://vleue.github.io/vleue_navigator/>

## 项目介绍
vleue_navigator是一款基于Bevy引擎的导航网格路径寻路库，依托Polyanya实现导航网格相关功能，可用于为Bevy游戏中的实体提供自动路径规划能力。支持从预构建的导航网格或动态障碍物实时生成导航网格，提供了WASM在线演示示例，兼容多个版本的Bevy引擎。

## 主要特性
1.  支持两种导航网格构建方式：从预导出的gLTF模型加载导航网格，或通过标记障碍物实体实时生成导航网格
2.  提供完整的路径寻路功能，可实现多智能体同时路径规划
3.  内置导航网格生成参数可调，支持自定义路径规划效果
4.  附带丰富的示例代码与官方文档，支持快速上手开发
5.  适配多个Bevy版本，兼容性覆盖0.13到0.19主流版本
