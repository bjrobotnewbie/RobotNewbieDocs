# realtime-vla

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/deployment/llm-deployment/realtime-vla/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

以 30Hz 帧率和 480Hz 轨迹频率运行 VLA

## 项目链接

- GitHub: <https://github.com/dexmal/realtime-vla>

## 项目介绍
本项目是realtime-vla，基于OpenPI项目的Pi0、Pi05及DM0模型，提供加速推理内核，实现VLA（视觉语言动作模型）的实时推理，支持30Hz推理帧率与480Hz轨迹频率，端到端延迟低于200ms，可用于机器人实时控制等场景，例如现实中捕捉下落笔的演示任务。

## 主要特性
1. 优化Pi0/Pi05内核、权重布局与执行调度，2026年9月更新后Pi0推理延迟降低11%-13%，Pi05降低20%，采用AI辅助内核参数搜索；
2. 新增DM0 Triton推理支持，提供`dm0_infer.py`；
3. 提供Pi0、Pi05的Triton推理实现，对应文件为`pi0_infer.py`、`pi05_infer.py`；
4. 新增`test.py`，支持Pi0、Pi05的Triton与JAX的正确性/一致性检查，含MAE及各维度MAE验证；
5. 提供RTX 4090/5090显卡下，1/2/3视图、不同模型的基准测试矩阵，适配不同摄像头帧率需求（1-2视图用30fps，3视图用25fps）。
