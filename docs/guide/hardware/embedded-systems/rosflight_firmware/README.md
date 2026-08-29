# rosflight_firmware

ROSflight 自动飞控固件

## 项目链接

- GitHub: <https://github.com/rosflight/rosflight_firmware>
- 项目主页: <http://rosflight.org/>

## 项目介绍
rosflight_firmware是ROSflight自动驾驶系统的核心固件库。ROSflight是一种软件架构，通过飞行控制器搭配运行ROS的 companion 计算机实现协同工作，二者间拥有高带宽连接，可高速获取传感器数据并下发 actuator 指令。该架构既可以通过嵌入式处理器直接控制底层功能，也能借助companion计算机和ROS实现视觉处理、算法优化等复杂功能。
本项目面向多旋翼、固定翼无人机，旨在降低先进自动驾驶代码的开发门槛，同时提供软件在环(SIL)仿真工具，采用经过同行评审的控制与估计算法，强调与ROS companion计算机的高带宽低延迟通信，方便科研人员快速开发、测试无人机代码。

## 主要特性
1.  降低无人机自动驾驶开发门槛，无需复杂嵌入式编程经验
2.  提供可靠的SIL仿真工具，支持快速迭代开发
3.  采用经过同行评审的核心算法，配套完整官方文档
4.  优先保障与ROS companion计算机的高速低延迟通信
5.  支持多旋翼、固定翼两种类型UAV
