# common_interfaces

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/common_interfaces/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

一组包含公共接口文件（.msg 和 .srv）的包。

## 项目链接

- GitHub: <https://github.com/ros2/common_interfaces>

## README 内容

# common_interfaces
A set of packages which contain common interface files (.msg and .srv).


## Purpose

Isolating the messages to communicate between stacks in a shared dependency allows nodes in dependent stacks to communicate without requiring dependencies upon each other.
This repository has been designed to contain the most common messages used between multiple packages to provide a shared dependency which will eliminate a problematic circular dependency.

## 贡献

关于如何贡献，请参考 [CONTRIBUTING.md](https://github.com/ros2/common_interfaces/blob/master/CONTRIBUTING.md)。
