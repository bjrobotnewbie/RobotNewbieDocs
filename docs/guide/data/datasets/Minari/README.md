# Minari

离线强化学习数据集的标准格式，包含热门参考数据集及相关工具

## 项目链接

- GitHub: <https://github.com/Farama-Foundation/Minari>
- 项目主页: https://minari.farama.org

## 项目概述

## 项目介绍
Minari是一款用于离线强化学习研究的Python库，对标离线版Gymnasium或HuggingFace数据集库的离线RL版本，提供了标准化的离线强化学习数据集格式，附带热门参考数据集与相关工具。官方文档站点为minari.farama.org，同时提供官方Discord社区用于交流与开发协作。

## 主要特性
1.  支持通过PyPI快速安装，可按需安装全量依赖或从源码编译用于开发测试
2.  提供命令行API，可实现远程/本地数据集查看、下载、详情展示等操作
3.  支持读取已有的离线RL数据集，可快速获取轨迹的观测、动作、奖励、终止信号等核心数据
4.  支持通过数据收集器包装Gymnasium环境，快速生成自定义离线RL数据集
5.  内置多款热门参考数据集，适配主流离线RL研究场景
