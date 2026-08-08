# rosdistro

本仓库维护了各 ROS 发行版的仓库列表。

## 项目链接

- GitHub: <https://github.com/ros/rosdistro>

## README 内容

This repository maintains two independent sets of packaging metadata used in ROS:

1. The lists of repositories that curate ROS packages for each ROS distributions,
   implementing the data structure defined in [REP 143](http://ros.org/reps/rep-0143.html).
   Any ROS package release will generate pull requests to the distribution files
   in this repository.

2. The rosdep rules database, which map the package names used in package.xml files to
   system package names.

### 贡献指南

更多贡献信息请参考 [CONTRIBUTING.md](https://github.com/ros/rosdistro/blob/master/CONTRIBUTING.md)。

### 审核准则

关于 PR 合并的审核标准，请参考 [REVIEW_GUIDELINES.md](https://github.com/ros/rosdistro/blob/master/REVIEW_GUIDELINES.md)。
