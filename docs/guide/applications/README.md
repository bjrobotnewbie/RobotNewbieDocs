# 机器人应用

机器人应用涵盖机器人技术在各个领域的具体落地场景和解决方案。本章节只放“用来做什么”的场景类内容；单个机器人本体形态归入机器人形态，多个机器人协同归入多机器人系统。

## 项目列表

- [农业机器人](/guide/applications/agricultural/README)
- [自动驾驶](/guide/applications/autonomous-driving/README)
- [具身通用人工智能](/guide/applications/embodied-agi/README)
- [工业机器人应用](/guide/applications/industrial/README)
- [医疗机器人应用](/guide/applications/medical/README)
- [服务机器人应用](/guide/applications/service/README)
- [无人机应用](/guide/applications/uav/README)
- [外骨骼机器人应用](/guide/applications/exoskeleton/README)
- [organicmaps（🍃 Organic Maps 是一款面向…）](/guide/applications/organicmaps/README)
- [text-to-cad（面向CAD、机器人技术与硬件设计的智能体…）](/guide/applications/text-to-cad/README)
- [CADAM（CADAM 是开源的文本转CAD网页应用）](/guide/applications/CADAM/README)
- [Trail-Sense（一款利用手机传感器为户外徒步旅行或生存场…）](/guide/applications/Trail-Sense/README)
- [robotics-skills-suite（76项符合合规审计要求的Claude技能…）](/guide/applications/robotics-skills-suite/README)
- [kachaka-api（智能家具平台「Kachaka」API）](/guide/applications/kachaka-api/README)
- [openmct（基于Web的任务控制框架。）](/guide/applications/openmct/README)
- [py-xiaozhi（集成MCP、支持多模态工作流与IoT、具…）](/guide/applications/py-xiaozhi/README)
- [dreame-vacuum（支持地图功能的追觅扫地机器人Home A…）](/guide/applications/dreame-vacuum/README)
- [Makelangelo-software（适用于绘图仪的软件——尤其是悬挂式极坐标…）](/guide/applications/Makelangelo-software/README)
- [Robots（创建并仿真ABB、KUKA、UR和Sta…）](/guide/applications/Robots/README)
- [OpenMower（让我们将廉价的现成商用割草机器人升级为基…）](/guide/applications/OpenMower/README)
- [xr_teleoperate（本仓库实现了基于 XR 设备的 Unit…）](/guide/applications/xr_teleoperate/README)
- [CTK（一套用于医学成像、手术导航及相关应用的通…）](/guide/applications/CTK/README)
- [PhysiClaw（与您在现实世界中互动的 AI 代理。）](/guide/applications/PhysiClaw/README)
## 分类说明

| 分类 | 核心应用领域 | 技术特点 |
|------|---------|---------|
| **工业机器人应用** | 制造业、自动化生产 | 高精度、高负载、连续作业 |
| **服务机器人应用** | 日常生活、公共服务 | 人机交互、自主导航、环境适应 |
| **农业机器人应用** | 农业生产、农田管理 | 环境感知、自动作业、农业物联网 |
| **医疗机器人应用** | 手术康复、辅助医疗 | 高精度、安全可靠、医学影像融合 |
| **自动驾驶应用** | 智能交通、移动出行 | 环境感知、决策规划、车辆控制 |
| **无人机应用** | 航拍测绘、物流运输、巡检救援、表演 | 自主飞行、远程操控、多传感器融合 |
| **具身 AGI 应用** | 通用具身智能 | 多模态感知、自主学习、通用任务完成 |
| **外骨骼机器人应用** | 康复医疗、工业助力、军事增强 | 人机协同、意图感知、力反馈 |

## 归类边界

- “无人机”是机器人形态；“无人机测绘/灯光秀”是应用场景。
- “无人机集群”是多机器人系统；“无人机集群表演”同时交叉引用无人机应用。
- “人形机器人”是机器人形态；“人形机器人在工业/服务中的使用”是应用场景。

## 形态-应用交叉引用机制

本知识库采用**单一职责 + 双向引用**的分类策略：

| 分类 | 职责 | 内容范围 |
|-----|------|---------|
| **robot-forms** | 形态描述 | 只描述机器人本体的结构类型、运动方式、机械结构 |
| **applications** | 场景描述 | 只描述机器人在具体行业和任务中的落地应用 |

### 双向引用规则

1. **形态 → 应用**：每个机器人形态分类底部添加「典型应用场景」表格，链接到本章节对应的应用场景
2. **应用 → 形态**：每个应用领域分类底部添加「常用机器人形态」表格，链接到形态分类对应的机器人类型

### 优点

- ✅ 避免内容重复存储
- ✅ 统一分类维度，用户查找路径清晰
- ✅ 形成知识网络，从任意入口都能找到关联内容
