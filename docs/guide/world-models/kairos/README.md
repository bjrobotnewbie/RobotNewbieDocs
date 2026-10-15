# kairos

世界模型 Kairos 官方代码

## 项目链接

- GitHub: <https://github.com/DAXIAORobotics/kairos>

## 项目介绍
Kairos是一款40亿参数的原生跨 embodied 世界模型，可用于统一的场景理解、内容生成与动作预测。它通过渐进式跨 embodied 数据课程，从通用视频、人类行为数据和真实机器人交互中学习，构建持久的世界表征。该模型基于World-Action Model架构与混合线性时间记忆，可联合预测未来视觉状态与可执行机器人动作，支持长时序推理、高质量内容生成，且可在边缘端实时部署，适用于 embodied AI 领域。

## 主要特性
1.  跨 embodied 统一建模：支持从多源数据学习通用世界表征
2.  联合预测能力：可同时生成未来视觉画面与可执行机器人动作
3.  轻量化部署：适配边缘端实时运行
4.  已开源多版本模型：包括Kairos3.1系列、预训练版与机器人专用版，可通过Hugging Face、Model Scope获取，配套推理代码已开源。
