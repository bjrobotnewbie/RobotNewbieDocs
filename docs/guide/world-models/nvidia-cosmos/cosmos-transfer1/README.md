# cosmos-transfer1

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/world-models/nvidia-cosmos/cosmos-transfer1/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Cosmos-Transfer1 是一个从世界到世界的转移模型，旨在弥合模拟环境与真实世界环境之间的感知鸿沟。

## 项目链接

- GitHub: <https://github.com/nvidia-cosmos/cosmos-transfer1>
- 项目主页: <https://research.nvidia.com/labs/dir/cosmos-transfer1>

## 项目介绍
Cosmos-Transfer1 是 NVIDIA Cosmos 世界基础模型（WFM）的核心分支，是一款用于弥合模拟环境与真实环境感知鸿沟的 world-to-world 迁移模型，专注于多模态可控条件世界生成或跨域迁移，支持基于 ControlNet 的单模态条件世界生成。该项目已停止主动开发，仅提供有限维护，建议用户迁移至新一代 Cosmos 3 平台以获取更先进的 Physical AI 能力。

## 主要特性
- 支持基于 ControlNet 的单模态条件世界生成，可基于分割视频、深度视频、边缘视频、模糊视频、LiDAR 视频或 HDMap 视频等信号模态输入，结合用户文本提示（可选输入 RGB 视频帧提示）生成对应视觉模拟视频；
- 提供 7B 参数量的各模态专用模型（如 Cosmos-Transfer1-7B [Depth]），支持自回归生成模式。
