# WorldEngine

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/WorldEngine/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

WorldEngine：迈向自动驾驶的无监督学习时代

## 项目链接

- GitHub: <https://github.com/OpenDriveLab/WorldEngine>
- 项目主页: <https://opendrivelab.com/WorldEngine/>

## 项目介绍
WorldEngine是面向自动驾驶后训练时代的开源基础设施，经过生产环境验证，旨在解决自动驾驶中长尾安全关键数据稀缺的问题，为自动驾驶物理AI提供后训练支持。项目包含多模块工具链，可用于自动驾驶模型的训练、微调以及闭环仿真测试，配套提供了公开数据集，可在Hugging Face和ModelScope平台获取。

## 主要特性
1.  覆盖三大核心模块：SimEngine提供照片级真实感闭环仿真能力，AlgEngine支持端到端模型训练与微调，Scene Reconstruction基于3D高斯溅射技术MTGS实现场景重建
2.  支持nuPlan等平台的闭环仿真测试，可完成夜间城市道路等真实场景的上路部署验证
3.  基于PyTorch 2.0.1与Python 3.9开发，采用Apache 2.0开源协议
4.  配套提供arxiv论文与演示视频，拥有完整的快速上手与深度开发文档
