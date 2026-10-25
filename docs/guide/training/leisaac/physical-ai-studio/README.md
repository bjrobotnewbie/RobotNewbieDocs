# physical-ai-studio

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/leisaac/physical-ai-studio/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

物理 AI 工作室是一个端到端的框架，用于通过人类演示的模仿学习训练机器人执行任务。

## 项目链接

- GitHub: <https://github.com/open-edge-platform/physical-ai-studio>

## 项目介绍
Physical AI Studio是一个端到端框架，用于通过人类演示的模仿学习训练机器人完成任务，支持训练和部署用于机器人模仿学习的视觉-语言-动作（VLA）模型。

## 主要特性
- 端到端流水线：覆盖从演示录制到机器人部署的全流程
- 先进策略：原生实现ACT、SmolVLA、Pi0.5、RLDX-1等策略，完整支持LeRobot策略库
- 灵活接口：提供Python API、CLI、GUI三种使用方式
- 多硬件部署：支持导出为OpenVINO、ONNX、Torch格式，适配各类硬件
- 标准化基准：可在LIBERO、PushT、RoboCasa等基准上评估模型
- 基于PyTorch Lightning构建：支持分布式训练、混合精度等功能
