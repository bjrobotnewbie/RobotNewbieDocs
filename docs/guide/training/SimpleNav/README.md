# SimpleNav

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/SimpleNav/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

SimpleNav: 一个简单、统一、可复现且可扩展的导航 VLA 研究框架。

## 项目链接

- GitHub: <https://github.com/OpenBMB/SimpleNav>
- 项目主页: <https://simplenav.github.io/>

## 项目介绍
SimpleNav是由清华大学THUNLP、AI9Stars、OpenBMB、HITDIP联合开源的导航VLA研究框架，核心目标是为导航VLA研究提供简单、统一、可复现、可扩展的研究流程，打通异构导航数据、长 horizon VLA 模型、训练与基准评估环节，支持空中与地面导航场景。

## 主要特性
1. 标准化模型、动作、产物与评估接口，支持跨数据集、任务、平台的高效复用、对比与扩展；
2. 配备专用适配器，保留特定数据集的坐标系与模拟器语义；
3. 提供数据转换、轨迹增强、图像采集、验证统计等工具，简化导航数据处理流程；
4. 支持Python 3.10，遵循MIT开源协议，配套完善的文档与基准评估结果。
