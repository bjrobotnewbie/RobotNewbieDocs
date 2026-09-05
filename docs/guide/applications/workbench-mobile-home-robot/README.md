# workbench-mobile-home-robot

具有有限动作、可重放事件和失效闭验证的轮式移动家机器人证据导向运行时。

## 项目链接

- GitHub: <https://github.com/Quchaosheng/workbench-mobile-home-robot>

## 项目介绍
本项目是一款轮式家用移动机器人的证据优先运行时框架，主打**先验证再完成任务**的开发理念。它支持有限动作集、可回放事件流，并能通过验证器输出`confirmed`、`refuted`或`insufficient evidence`三种验证结果，避免将“指令已接收”等同于“任务已完成”。
项目基于Python 3.12开发，无需GPU即可运行离线 runtime，提供了从意图选择、执行到验证、回放的完整机器人任务链路，还可搭配独立的OmniLink AI知识层使用。

## 主要特性
1.  采用证据优先的验证逻辑，基于实际执行证据给出明确验证结论
2.  严格的JSON Schema与Pydantic数据契约，保障数据合法性
3.  基于SQLite的追加式事件存储，支持完整性校验与事件回放
4.  针对有限语义动作的失败关闭策略验证
5.  提供只读可视化面板与确定性仿真测试用例
6.  适配MCU、CAN、运动控制与板级支持包的软件分层基础框架
