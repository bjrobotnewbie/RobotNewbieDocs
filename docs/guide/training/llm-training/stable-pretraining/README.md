# stable-pretraining

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/llm-training/stable-pretraining/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

可靠、精简且可扩展的预训练基础模型与世界模型库

## 项目链接

- GitHub: <https://github.com/galilai-group/stable-pretraining>
- 项目主页: <https://galilai-group.github.io/stable-pretraining/>

## 项目介绍
stable-pretraining是一个可靠、极简且可扩展的预训练库，用于预训练基础模型与世界模型，基于PyTorch Lightning构建，核心功能是帮助研究人员对比和自定义自监督学习方法，支持自定义前向函数、在线探针、表征诊断，以及训练、评估、 checkpointing 等流程。

## 主要特性
1. 内置多种自监督学习方法，包括SimCLR、DINO、MAE、BYOL、VICReg、LeJEPA等
2. 提供实验性JAX后端支持
3. 集成训练管理功能，支持 checkpointing、训练恢复、本地实验注册
4. 支持自定义图像、在线评估等扩展场景
5. 提供CLI工具简化使用，具备完善的测试覆盖与文档支持，遵循MIT开源协议
