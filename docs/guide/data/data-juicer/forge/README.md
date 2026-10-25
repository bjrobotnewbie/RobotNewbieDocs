# forge

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/data-juicer/forge/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

机器人数据工具包 | 支持在 RLDS、LeRobot v2/v3、Zarr、HDF5 和 Rosbag 等格式间转换。可检查、可视化并分析数据集。与 HuggingFace Hub 兼容。专为 OpenVLA、Octo、LeRobot 和 Diffusion Policy 工作流构建。

## 项目链接

- GitHub: <https://github.com/arpitg1304/forge>

## 项目介绍
forge是一款机器人数据工具包（Robotics Data Toolkit），核心功能为机器人数据集格式转换、处理与管理，支持RLDS、LeRobot v2/v3、Zarr、HDF5、Rosbag等主流机器人数据集格式，可对接HuggingFace Hub，适配OpenVLA、Octo、LeRobot、Diffusion Policy等机器人工作流。

## 主要特性
1. 格式工具能力：支持数据集的转换、检查、评分、过滤、分段、可视化等操作，兼容本地路径、`hf://`数据集、S3/GS存储桶；
2. 数据引擎能力：可将采集的数据集条目注册为可查询的追加式目录，支持SQL查询、自然语言语义搜索、去重与整理，还提供可视化Studio用于数据集探索；
3. 灵活安装：提供基础版与全量版安装选项，可按需选择RLDS、LeRobot、S3、GCS等扩展依赖。
