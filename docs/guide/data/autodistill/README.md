# autodistill

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/data/autodistill/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

无标注图像推理（利用基础模型训练监督模型）

## 项目链接

- GitHub: <https://github.com/autodistill/autodistill>
- 项目主页: <https://docs.autodistill.com>

## 项目介绍
autodistill是一款基于基础模型的自动化标注与模型蒸馏工具，核心功能是利用大型基础模型训练小型高效的监督模型，可实现从无标注图像到边缘端自定义模型推理的全流程自动化，无需人工干预。支持在本地硬件或Roboflow托管版本上运行，当前聚焦视觉任务，未来可扩展至语言等其他模型领域。

## 主要特性
- 提供可插拔接口，支持模型间灵活连接
- 自动完成数据集标注
- 可训练快速的监督模型
- 支持自主掌控模型所有权
- 支持将蒸馏后的模型部署至云端或边缘端
- 适配Python多版本，提供Colab教程与官方文档，便于快速上手
