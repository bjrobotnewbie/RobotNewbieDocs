# GPT-Policy

基于视觉语言模型（VLM）的上下文机器人学习

## 项目链接

- GitHub: <https://github.com/cheng-haha/GPT-Policy>
- 项目主页: <https://cheng-haha.github.io/GPT-Policy/>

## 项目介绍
GPT-Policy是一个基于VLM（视觉语言模型）智能体的闭环机器人控制框架，核心实现了上下文机器人学习能力。该框架将固定VLM与机器人工具连接，部署阶段无需梯度更新或任务特定参数调整，即可利用演示示例、目标图像、交互历史及执行反馈完成机器人控制。目前已提供ARX X5和I2RT/YAM两款机械臂平台的硬件适配器，相关研究成果已发布论文《In-Context Robot Learning with VLM Agents》。

## 主要特性
1. 采用VLM智能体实现闭环机器人控制，支持上下文机器人学习
2. 部署阶段无需梯度更新或任务特定参数调整，适配灵活
3. 提供两款主流机械臂平台的硬件适配器，可快速集成使用
