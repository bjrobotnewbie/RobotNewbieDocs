# UnifoLM-VLA-0
宇树科技（Unitree Robotics）开源的UnifoLM系列面向通用人形机器人操作的视觉-语言-动作(VLA)大模型，突破传统VLM在物理交互中的局限，通过在机器人操作数据上持续预训练，实现从"图文理解"到具备物理常识"具身大脑"的进化。

## 核心特性
- 基于Qwen2.5-VL-7B基座，仅用340小时高质量真机数据完成预训练，数据效率极高
- 空间语义增强技术，深度融合文本指令与2D/3D空间细节，显著增强空间感知和几何理解能力
- 集成动作分块预测+双向动力学约束，为模型植入"微型物理引擎"，支持长时序动作规划
- 在LIBERO仿真基准取得平均98.7%的惊人成绩（99.0/100/99.4/96.2）
- 无思考模式下空间推理能力可比肩Google Gemini-Robotics-ER 1.5
- 单一策略即可完成宇树G1人形机器人12类复杂操作任务，抗干扰能力强

## 相关链接
- 📦 GitHub仓库：[https://github.com/unitreerobotics/unifolm-vla](https://github.com/unitreerobotics/unifolm-vla)
- 🤗 HuggingFace权重：[https://huggingface.co/unitreerobotics/UnifoLM-VLA-Base](https://huggingface.co/unitreerobotics/UnifoLM-VLA-Base)
- 🐼 ModelScope权重：[https://modelscope.cn/models/unitreerobotics/UnifoLM-VLA-Base](https://modelscope.cn/models/unitreerobotics/UnifoLM-VLA-Base)
- 🏠 项目主页：[https://unigen-x.github.io/unifolm-vla.github.io/](https://unigen-x.github.io/unifolm-vla.github.io/)
