# trajopt

ROS 轨迹优化运动规划器

## 项目链接

- GitHub: <https://github.com/tesseract-robotics/trajopt>

## 项目介绍
trajopt_ros是一款针对ROS的轨迹优化运动规划器，基于序列凸优化算法求解机器人运动规划问题，通过惩罚方法在约束条件下优化关节速度，支持多平台编译部署，已通过Linux、Mac OSX、Windows等环境的CI测试。

## 主要特性
1.  支持多种凸求解器：默认使用OSQP，还兼容BPMPD、Gurobi、qpOASES，其中BPMPD已内置，OSQP和qpOASES可自动拉取源码，Gurobi需手动配置环境变量
2.  满足约束条件下的轨迹优化，可生成平滑的机器人运动路径
3.  采用Apache 2.0和BSD 2条款双开源许可，支持级别为工业ROS联盟级支持
4.  适配多操作系统，提供完善的代码质量检查流程
