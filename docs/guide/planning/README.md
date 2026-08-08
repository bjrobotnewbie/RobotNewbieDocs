# 机器人规划 (Robot Planning)

机器人规划是指机器人根据任务目标和环境信息，生成合理的行动序列和运动轨迹的过程。规划是机器人智能化的核心能力，根据抽象层级和应用场景分为三个主要方向。

## 三大规划层级

| 层级 | 英文名称 | 抽象程度 | 核心问题 | 典型输出 |
|------|---------|---------|---------|---------|
| **任务规划** | Task Planning | 最高 | "做什么？" | 子任务序列 |
| **运动规划** | Motion Planning | 中间 | "怎么动？" | 关节/末端轨迹 |
| **路径规划** | Path Planning | 最低 | "走哪条？" | 几何路径点 |

---

## 分类导航

- [运动规划 (Motion Planning)](./motion-planning/README)：机械臂运动规划框架、算法库、轨迹优化、避障与局部规划
- [任务规划 (Task Planning)](./task-planning/README)：行为树、HTN、PDDL、LLM 驱动规划与搜索博弈算法
- [路径规划 (Path Planning)](./path-planning/README)：A*、RRT*、DWA 等经典寻路算法

---

> 运动规划与任务规划相关的具体库与工具已归入对应分组，详见：
> - [运动规划 (Motion Planning)](./motion-planning/README)：curobo、MPlib、openrave、tesseract、pyroboplan、roboplan、python_motion_planning、dynoplan、ruckig、toppra、cuTAMP、HRVO、RVO2、RVO2-3D、RVO2-CS、SCAN-Planner 等
> - [任务规划 (Task Planning)](./task-planning/README)：BehaviorTree.CPP、bonsai、ros2_planning_system、mctx、open_spiel 等

## 路径规划与覆盖规划

- [FC-Planner](/guide/planning/FC-Planner/README) - 骨架引导的三维覆盖路径规划，用于无人机自主巡检
- [Fields2Cover](/guide/planning/Fields2Cover/README) - 面向自主农业车辆的覆盖路径规划库
- [ft-fsd-path-planning](/guide/planning/ft-fsd-path-planning/README) - 无人方程式赛车路径规划算法
- [pathplanner](/guide/planning/pathplanner/README) - FRC 竞赛机器人运动轮廓生成工具
- [AutonomousVehicleControlBeginnersGuide](/guide/planning/AutonomousVehicleControlBeginnersGuide/README) - 自动驾驶算法学习示例集

## 高级规划与重建

- [MAGICIAN](/guide/planning/MAGICIAN/README) - 基于 Imagined Gaussians 的长期规划与主动建图
- [PredRecon](/guide/planning/PredRecon/README) - 预测增强型规划框架，用于自主空中 3D 重建

---

## 技术选型建议

| 机器人类型 | 主要规划需求 | 推荐技术组合 |
|-----------|-------------|-------------|
| **移动机器人** | 导航避障 | 路径规划 (A* + DWA) |
| **机械臂** | 操作抓取 | 运动规划 (MoveIt! + OMPL) |
| **服务机器人** | 任务+运动 | 任务规划 (LLM) + 运动规划 |
| **人形机器人** | 全栈规划 | 三层规划协同 |

---

## 与其他目录的关系

| 目录 | 关系说明 |
|------|---------|
| **navigation/** | 导航技术栈（SLAM、建图），为路径规划提供环境信息 |
| **control/** | 底层运动控制，执行规划器输出的轨迹 |
| **embodied-models/vln/** | 视觉语言导航模型，端到端生成导航策略 |
| **embodied-models/vla/** | 视觉语言动作模型，端到端生成机器人动作 |
