# GameWAM

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/GameWAM/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

GameWAM：视频游戏世界动作模型

## 项目链接

- GitHub: <https://github.com/yunncheng/GameWAM>
- 项目主页: <https://yunncheng.github.io/GameWAM/>

## 项目介绍
GameWAM是首个面向原生闭环游戏玩法与GUI控制的世界动作模型，用于解决现有游戏智能体缺乏显式世界动态建模、交互式游戏世界模型无法直接作为任务策略的问题。它通过并行视觉与动作生成流程，结合块因果条件与流匹配技术，联合生成未来视觉观测与可执行键鼠轨迹；在线控制时可预测超出已提交动作范围的内容，执行短前缀动作后观测环境状态并重新规划。

## 主要特性
1. 支持原生闭环游戏玩法与GUI控制，适配Minecraft、ViZDoom、VoxeLibre等游戏场景
2. 提供模型权重、游戏数据集（Minecraft、ViZDoom），可通过Hugging Face获取
3. 采用Hydra管理模型、数据、任务及模拟器配置，支持多任务评估与零样本评估
