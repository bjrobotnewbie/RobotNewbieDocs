# WareTwin

实时 3D 自主仓储数字孪生——20 台 AMR 确定性仿真、可解释车队调度、故障注入、视觉语言模型（VLM）相机感知、AI 运维助手及情景模拟。基于 React Three Fiber 与 FastAPI 构建。

## 项目链接

- GitHub: <https://github.com/WayneChou-bot/WareTwin>
- 项目主页: <https://ware-twin.vercel.app>
- 中文文档: https://github.com/waynechou-bot/waretwin/blob/main/README.zh-TW.md

## 项目介绍
WareTwin是一款浏览器原生的自主仓库3D数字孪生项目，可在真实部署前模拟机器人车队、运营事件、AI决策与假设场景。它支持20台自主移动机器人(AMR)的实时仿真，搭载确定性仿真引擎、可解释调度系统、VLM视觉感知与AI运维助手，技术栈为React Three Fiber + FastAPI，无需RTX显卡、ROS或云服务即可在集成GPU的笔记本上运行，还提供在线演示版本。

## 主要特性
1.  **3D数字孪生**：基于`warehouse_layout.json`快速搭建仓库场景，支持实时A*路径、流量热力图、多画质档位适配集成显卡
2.  **机器人车队仿真**：100ms确定性仿真引擎，实现完整机器人状态机、交通权重网格A*规划、死锁处理、电池与充电调度
3.  **可解释车队调度**：任务分配会展示选中机器人的选择依据与落选机器人的淘汰原因
4.  **场景注入测试**：一键触发并可逆模拟机器人故障、 conveyor停机、人员闯入、流量拥堵等各类异常场景
5.  集成VLM视觉感知、异常预测与运维解释功能，支持虚拟CCTV监控
