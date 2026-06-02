# BYOVLA (Bring Your Own VLA)
Princeton University 开源的运行时干预VLA增强方法，无需微调即可提升复杂场景下VLA模型性能，对干扰物体和背景鲁棒性更强。

## 核心特性
- 运行时干预增强方案，无需微调也无需访问模型权重
- 通过图像预处理提升VLA在干扰物体场景性能
- 结合 Grounded SAM 分割+大语言模型 refinement+inpaint 去除干扰
- 即插即用，可以配合任何已训练好的VLA模型使用
- 在已有VLA输出基础上提升性能，几乎不增加推理延迟

## 相关链接
- 📦 GitHub仓库：[https://github.com/irom-princeton/byovla](https://github.com/irom-princeton/byovla)
- 📄 论文：[Visually Robust VLAs](https://aasherh.github.io/data/Hancock_Visually_Robust_VLAs.pdf)
- 🏠 项目主页：[https://aasherh.github.io/byovla/](https://aasherh.github.io/byovla/)
