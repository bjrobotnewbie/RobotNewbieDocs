# 具身数据

具身数据是机器人学习和智能决策的基础，包括数据集、基准评测、数据采集工具和数据生成管道。本章节涵盖机器人领域常见的数据基础设施。

## 分类列表

### 基准与评测

- [基准数据集](./benchmark_data/README)：CALVIN、LIBERO、Meta-World、RoboTwin 2.0、SimplerENV 等标准基准，用于算法对比和模型评估
- [Embodied Agent Interface](./benchmark_data/embodied-agent-interface/README)：具身智能 LLM 高层决策评测基准
- [RoboGen](./benchmark_data/robogen/README)：自动化生成机器人学习资源的数据生成框架
- [FluxBisim](./benchmark_data/fluxbisim/README)：FluxVLA 生态系统机器人 VLA 模型评测基准

### 机器人数据集

- [机器人数据集](./datasets/README)：AgiBot World、Open X-Embodiment、DROID、BridgeData V2 等大规模机器人操作数据集

### 数据采集

- [机器人数据采集](./data-collection/README)：动作捕捉系统（PNP、FlashCap、DexCap、EasyMocap 等）和遥操作采集（XR Teleoperate、IsaacTeleop 等）

### 数据生成与管理

以下项目已归入对应分组：

- [GRAIL](/guide/data/GRAIL/README)、[Rerun](/guide/data/rerun/README)、[bagel](/guide/data/bagel/README) 已归入 [机器人数据采集](./data-collection/README)
- [KungFuAthleteBot](/guide/data/KungFuAthleteBot/README)、[PHUMA](/guide/data/PHUMA/README)、[DroneDB](/guide/data/DroneDB/README) 已归入 [机器人数据集](./datasets/README)

## 分类说明

| 分类 | 主要内容 | 应用场景 |
|------|---------|---------|
| **基准数据集** | 标准基准与评测环境 | 算法对比，模型评估 |
| **机器人数据集** | 大规模真实/仿真机器人数据 | 机器人学习，模型训练 |
| **数据采集** | 动作捕捉、遥操作采集 | 构建演示数据集，模仿学习 |
| **数据生成与管理** | 数据生成管道、运动数据集、可视化工具 | 数据基础设施，数据质量管理 |

## 数据在机器人学习中的重要性

高质量数据是机器人学习的基础：

- **模仿学习**：需要高质量的人类演示数据
- **强化学习**：需要大规模交互数据
- **仿真到现实**：准确采集帮助降低域差距
- **泛化能力**：多样化数据提升模型鲁棒性

- [bagel（与您的机器人、无人机和物联网数据对话——…）](/guide/data/bagel/README)

- [DroneDB（用于地理空间数据存储的自由开源软件。）](/guide/data/DroneDB/README)
