# 具身智能基础模型层 (Foundation Models for Embodied AI)

基础模型层分为三个主要方向：

## 视觉语言动作模型 (VLA)

直接将视觉输入和自然语言指令映射到机器人动作序列，是当前具身智能机器人的主流范式。

### 项目列表

- [LingBot-VLA](/guide/embodied-models/vla/lingbot-vla/README.md)
- [FluxVLA Engine](/guide/embodied-models/vla/fluxvla/README.md)
- [OpenVLA](/guide/embodied-models/vla/openvla/README.md)
- [UnifoLM-VLA-0](/guide/embodied-models/vla/unifolm-vla/README.md)
- [OpenPI (PI-Zero)](/guide/embodied-models/vla/openpi/README.md)
- [GR00T-N1.7](/guide/embodied-models/vla/gr00t/README.md)
- [MolmoAct2](/guide/embodied-models/vla/molmoact/README.md)
- [SmolVLA](/guide/embodied-models/vla/smolvla/README.md)
- [Octo](/guide/embodied-models/vla/octo/README.md)
- [X-VLA](/guide/embodied-models/vla/x-vla/README.md)
- [StarVLA](/guide/embodied-models/vla/starvla/README.md)
- [WALL-OSS](/guide/embodied-models/vla/wall-oss/README.md)
- [XL-VLA](/guide/embodied-models/vla/xl-vla/README.md)
- [BYOVLA](/guide/embodied-models/vla/byovla/README.md)
- [RT-2](/guide/embodied-models/vla/rt-2/README.md)
- [F1-VLA](/guide/embodied-models/vla/f1-vla/README.md)
- [VLA-JEPA](/guide/embodied-models/vla/vla-jepa/README.md)
- [VideoVLA](/guide/embodied-models/vla/videovla/README.md)
- [UD-VLA](/guide/embodied-models/vla/ud-vla/README.md)
- [VLA-RFT](/guide/embodied-models/vla/vla-rft/README.md)

## 世界动作模型 (WAM)

世界动作模型（WAM）通过预测未来世界状态来学习物理动力学，具备更强的泛化能力和物理直觉。

### 项目列表

- [DreamZero](/guide/embodied-models/wam/dreamzero/README.md)
- [Cosmos Policy](/guide/embodied-models/wam/cosmos-policy/README.md)
- [UnifoLM-WMA-0](/guide/embodied-models/wam/unifolwm/README.md)
- [Awesome-WAM](/guide/embodied-models/wam/awesome-wam/README.md)
- [TesserAct](/guide/embodied-models/wam/tesseract/README.md)
- [Large Video Planner](/guide/embodied-models/wam/lvp/README.md)
- [4DGen](/guide/embodied-models/wam/4dgen/README.md)
- [LaPA](/guide/embodied-models/wam/lapa/README.md)
- [mimic-video](/guide/embodied-models/wam/mimic-video/README.md)
- [villa-X](/guide/embodied-models/wam/villa-x/README.md)
- [WorldVLA](/guide/embodied-models/wam/worldvla/README.md)
- [RynnVLA-002](/guide/embodied-models/wam/rynnvla-002/README.md)
- [GigaWorld-Policy](/guide/embodied-models/wam/gigaworld-policy/README.md)
- [FRAPPE](/guide/embodied-models/wam/frappe/README.md)
- [Motus](/guide/embodied-models/wam/motus/README.md)
- [Diffusion Reward](/guide/embodied-models/wam/diffusion-reward/README.md)
- [SRPO](/guide/embodied-models/wam/srpo/README.md)
- [WoVR](/guide/embodied-models/wam/wovr/README.md)
- [Interactive World Simulator](/guide/embodied-models/wam/interactive-world-sim/README.md)

## 视觉语言导航 (VLN)

让机器人根据自然语言指令在环境中自主导航到目标位置，是具身导航的核心任务。

### 项目列表

- [CLIPort](/guide/embodied-models/vln/cliport/README.md)
- [VLN-BERT](/guide/embodied-models/vln/vln-bert/README.md)
- [DUET](/guide/embodied-models/vln/duet/README.md)
- [DualVLN](/guide/embodied-models/vln/dualvln/README.md)
- [SkillNav](/guide/embodied-models/vln/skillnav/README.md)
- [UrbanNav](/guide/embodied-models/vln/urbannav/README.md)
- [JanusVLN](/guide/embodied-models/vln/janusvln/README.md)

## 分类说明

| 分类 | 核心思想 | 优势 |
|------|---------|------|
| **VLA** | (图像, 语言) → 动作 直接映射 | 架构简洁，推理速度快 |
| **WAM** | 学习预测未来世界状态，泛化能力更强 | 具备物理直觉，零样本泛化能力强 |
| **VLN** | 语言导航，根据指令找到目标位置 | 长期导航任务，具身导航核心 |
