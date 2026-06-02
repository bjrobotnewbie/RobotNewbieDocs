# 具身智能基础模型层 (Foundation Models for Embodied AI)

基础模型层分为三个主要方向：

## 视觉语言动作模型 (VLA)

直接将视觉输入和自然语言指令映射到机器人动作序列，是当前具身智能机器人的主流范式。

### 项目列表

- [LingBot-VLA](foundation-models/vla/lingbot-vla/README.md)
- [FluxVLA Engine](foundation-models/vla/fluxvla/README.md)
- [OpenVLA](foundation-models/vla/openvla/README.md)
- [UnifoLM-VLA-0](foundation-models/vla/unifolm-vla/README.md)
- [OpenPI (PI-Zero)](foundation-models/vla/openpi/README.md)
- [GR00T-N1.7](foundation-models/vla/gr00t/README.md)
- [MolmoAct2](foundation-models/vla/molmoact/README.md)
- [SmolVLA](foundation-models/vla/smolvla/README.md)
- [Octo](foundation-models/vla/octo/README.md)
- [X-VLA](foundation-models/vla/x-vla/README.md)
- [StarVLA](foundation-models/vla/starvla/README.md)
- [WALL-OSS](foundation-models/vla/wall-oss/README.md)
- [XL-VLA](foundation-models/vla/xl-vla/README.md)
- [BYOVLA](foundation-models/vla/byovla/README.md)
- [RT-2](foundation-models/vla/rt-2/README.md)
- [F1-VLA](foundation-models/vla/f1-vla/README.md)
- [VLA-JEPA](foundation-models/vla/vla-jepa/README.md)
- [VideoVLA](foundation-models/vla/videovla/README.md)
- [UD-VLA](foundation-models/vla/ud-vla/README.md)
- [VLA-RFT](foundation-models/vla/vla-rft/README.md)

## 世界动作模型 (WAM)

世界动作模型（WAM）通过预测未来世界状态来学习物理动力学，具备更强的泛化能力和物理直觉。

### 项目列表

- [DreamZero](foundation-models/wam/dreamzero/README.md)
- [Cosmos Policy](foundation-models/wam/cosmos-policy/README.md)
- [UnifoLM-WMA-0](foundation-models/wam/unifolwm/README.md)
- [Awesome-WAM](foundation-models/wam/awesome-wam/README.md)
- [TesserAct](foundation-models/wam/tesseract/README.md)
- [Large Video Planner](foundation-models/wam/lvp/README.md)
- [4DGen](foundation-models/wam/4dgen/README.md)
- [LaPA](foundation-models/wam/lapa/README.md)
- [mimic-video](foundation-models/wam/mimic-video/README.md)
- [villa-X](foundation-models/wam/villa-x/README.md)
- [WorldVLA](foundation-models/wam/worldvla/README.md)
- [RynnVLA-002](foundation-models/wam/rynnvla-002/README.md)
- [GigaWorld-Policy](foundation-models/wam/gigaworld-policy/README.md)
- [FRAPPE](foundation-models/wam/frappe/README.md)
- [Motus](foundation-models/wam/motus/README.md)
- [Diffusion Reward](foundation-models/wam/diffusion-reward/README.md)
- [SRPO](foundation-models/wam/srpo/README.md)
- [WoVR](foundation-models/wam/wovr/README.md)
- [Interactive World Simulator](foundation-models/wam/interactive-world-sim/README.md)

## 视觉语言导航 (VLN)

让机器人根据自然语言指令在环境中自主导航到目标位置，是具身导航的核心任务。

### 项目列表

- [CLIPort](foundation-models/vln/cliport/README.md)
- [VLN-BERT](foundation-models/vln/vln-bert/README.md)
- [DUET](foundation-models/vln/duet/README.md)
- [DualVLN](foundation-models/vln/dualvln/README.md)
- [SkillNav](foundation-models/vln/skillnav/README.md)
- [UrbanNav](foundation-models/vln/urbannav/README.md)
- [JanusVLN](foundation-models/vln/janusvln/README.md)

## 分类说明

| 分类 | 核心思想 | 优势 |
|------|---------|------|
| **VLA** | (图像, 语言) → 动作 直接映射 | 架构简洁，推理速度快 |
| **WAM** | 学习预测未来世界状态，泛化能力更强 | 具备物理直觉，零样本泛化能力强 |
| **VLN** | 语言导航，根据指令找到目标位置 | 长期导航任务，具身导航核心 |
