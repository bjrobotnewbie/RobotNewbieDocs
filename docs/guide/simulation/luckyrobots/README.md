# luckyrobots

luckyrobots 是 LuckyEngine 机器人仿真的 Python SDK，通过 gRPC 控制机器人、策略、关节和 RL 合约。

## 项目链接

- GitHub: <https://github.com/luckyrobots/luckyrobots>
- 项目主页: https://luckyrobots.com

## 项目概述

luckyrobots 为 LuckyEngine 提供 Python 客户端接口，面向超真实 MuJoCo 机器人仿真。它覆盖引擎暴露的 gRPC 功能，包括机器人和策略发现、关节和执行器控制、运动图、逆运动学、RL contract、遥测、相机、视口、会话录制与回放等。

项目适合希望用 Python 快速连接仿真引擎、驱动机器人策略、构建 Gymnasium 环境或记录实验数据的用户。它强调“发现式”接口和合约驱动 RL 控制，使研究者可以围绕 LuckyEngine 构建训练、评估和可视化工作流，而不必直接处理底层引擎通信细节。
