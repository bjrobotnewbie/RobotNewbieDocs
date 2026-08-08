# common_interfaces

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
