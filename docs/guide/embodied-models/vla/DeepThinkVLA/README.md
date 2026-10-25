# DeepThinkVLA

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/vla/DeepThinkVLA/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

DeepThinkVLA：增强视觉语言 - 动作模型推理能力

## 项目链接

- GitHub: <https://github.com/OpenBMB/DeepThinkVLA>
- 项目主页: <https://arxiv.org/abs/2511.15669>

## 项目介绍
DeepThinkVLA是一款用于增强视觉语言动作（VLA）模型推理能力的项目，基于公开的pi0-FAST checkpoint重构出29亿参数的混合解码器架构，在生成动作前先输出推理轨迹。项目结合具身思维链（CoT）监督微调与结果导向强化学习，在LIBERO基准测试中取得97.0%的平均成功率。

## 主要特性
1.  采用混合注意力解码器，将自回归推理与并行动作生成分离，在保证控制精度的同时缩小延迟差距
2.  搭建两阶段CoT数据引擎：通过云端大视觉语言模型（LVLM）提取关键帧，再通过微调后的本地VLM扩展至完整轨迹
3.  仅架构本身就比朴素自回归CoT变体提升15.5%的成功率，强化学习微调还能在LIBERO-Long任务上再提升2.0%的成功率
4.  配套提供HuggingFace数据集与模型权重，已完成LIBERO及LIBERO Plus零样本测试。
