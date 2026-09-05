# omnisim

开源机器人模拟器：支持 HTTP/JSON 与 MCP 控制，采用牛顿物理引擎，配备 WGPU 渲染，集成 ROS 2，并提供可复现的基准测试。

## 项目链接

- GitHub: <https://github.com/omnilink-tech/omnisim>
- 项目主页: <https://www.omnilink-agents.com/omnisim>

## 项目介绍
OmniSim是一款开源机器人模拟器，专为智能体编程设计。它支持通过HTTP/JSON协议与MCP服务器交互，可通过自然语言描述快速搭建场景、编写控制器，内置Newton物理引擎与wgpu渲染能力，同时兼容ROS 2，可用于复现机器人仿真基准测试。该项目部分代码由AI智能体在人类指导下完成，提供了Claude Code/Cursor的MCP服务端以及ROS 2辅助工具包。

## 主要特性
1.  支持HTTP/JSON交互，可通过对话快速构建场景、调试控制器，支持热重载
2.  仅基于Newton物理引擎，支持刚体、布料与软体物理模拟
3.  内置wgpu渲染能力，可快速获取仿真场景截图
4.  原生兼容ROS 2，支持`simulation_interfaces`标准接口
5.  可用于机器人智能体训练、算法验证与复现仿真基准测试
6.  目前提供Windows预编译包，Linux支持源码编译，暂不支持macOS
