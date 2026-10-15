# awesome-microduck

Pollen Robotics / Hugging Face Microduck 机器人软件、模拟器、策略、代理工具及覆盖率精选列表

## 项目链接

- GitHub: <https://github.com/joeynyc/awesome-microduck>
- 项目主页: <https://microduckhub.com>

## 项目介绍
本项目是Pollen Robotics与Hugging Face联合推出的开源双足机器人Microduck的精选资源汇总列表。Microduck为25cm高、约800g的鸭形双足机器人，配备15个电机、摄像头、8×8ToF深度传感器、双IMU和抓取喙。其内置的行走、站坐、踢腿等行为均为在MuJoCo中训练并导出为ONNX格式的神经策略，完整的仿真到实物迁移栈采用Apache-2.0开源协议。当前处于预售阶段，预计2026年圣诞节前发货。

## 主要特性
1.  **覆盖范围全面**：包含官方资源、文档、仿真训练工具、策略技能、数据集基准、智能体工具等全生态内容
2.  **仿真优先**：官方浏览器沙箱、`microduck_rl`工具及已发布的ONNX策略可在无实体机器人的情况下运行验证
3.  **标准化策略分发**：官方已将内置策略上传至Hugging Face Hub，支持通过`robotctl`工具进行策略管理与安装
4.  **完整开源栈**：提供从仿真训练到实物部署的全流程开源代码，支持sim-to-real开发流程
