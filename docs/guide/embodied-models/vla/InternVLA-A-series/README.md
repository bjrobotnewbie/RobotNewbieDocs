# InternVLA-A-series

InternVLA-A1：统一理解、生成与动作的机器人操作

## 项目链接

- GitHub: <https://github.com/InternRobotics/InternVLA-A-series>

## 项目介绍
InternVLA-A-series（当前最新版本为InternVLA-A1.5）是面向机器人操作任务的统一视觉语言机器人策略模型，旨在整合视觉语言理解、视觉前瞻预测与动作生成能力，提升机器人操作的组合泛化能力。项目基于Qwen3.5-2B VLM骨干网络，提供了论文、项目主页、数据集与模型的开源下载渠道，原A1版本代码已迁移至`InternVLA-A1`分支。

## 主要特性
1.  **统一架构**：通过共享全注意力层为Qwen3.5-2B VLM挂载轻量统一动作专家，保留模态专属的Gated DeltaNet处理模块
2.  **视觉前瞻**：引入可学习前瞻令牌从多模态上下文查询任务相关的未来动态，训练阶段通过冻结的WAN2.2-5B视频生成模型进行监督
3.  **高效部署**：推理阶段舍弃视频分支，通过流匹配预测连续动作块，保证部署延迟可控
4.  **性能优异**：在RoboTwin 2.0、LIBERO、SimplerEnv等多个仿真基准与真实机器人操作场景中取得领先指标，例如在RoboTwin 2.0上达到93.2%准确率
5.  提供多个预训练版本，可通过HuggingFace和ModelScope下载。
