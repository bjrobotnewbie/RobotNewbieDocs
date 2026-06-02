# 运动规划算法库

运动规划算法库提供底层的规划算法实现，供研究人员和开发者进行二次开发和定制。这些库通常专注于规划算法本身，不包含完整的机器人集成框架。

## 库概览

| 库 | 核心算法 | 规划类型 | 特点 |
|----|---------|---------|------|
| [**OMPL**](/guide/planning/motion-planning/libraries/ompl/README.md) | RRT*, PRM, EST 等 | 基于采样 | 算法丰富，高性能 |
| [**SBPL**](/guide/planning/motion-planning/libraries/sbpl/README.md) | A*, ARA*, R* | 基于搜索 | 最优性保证，增量规划 |

## 算法分类对比

### 基于采样的规划 (OMPL)

OMPL 专注于基于采样的运动规划算法，适合高维构型空间的运动规划。

**核心特点：**
- ✅ 概率完备性
- ✅ 高维空间效率高
- ✅ 算法选择丰富
- ✅ 纯 C++ 实现

**典型算法：**
- **RRT/RRT***：快速扩展随机树及其最优版本
- **PRM**：概率路线图
- **EST**：扩展空间树
- **KPIECE**：基于网格的探索

**适用场景：**
- 机械臂运动规划
- 高维系统（7+自由度）
- 复杂环境避障
- 研究和算法开发

---

### 基于搜索的规划 (SBPL)

SBPL 专注于基于图搜索的规划算法，提供最优性保证和增量规划能力。

**核心特点：**
- ✅ 有界次优性保证
- ✅ Anytime 规划能力
- ✅ 增量规划支持
- ✅ 状态格表示

**典型算法：**
- **A***：经典启发式搜索
- **ARA***：任意时间 A*
- **ANA***：自适应非参数 A*
- **R***：增量路径修复

**适用场景：**
- 移动机器人导航
- 需要最优解的场景
- 动态环境重规划
- 时间受限系统

## 技术对比

| 特性 | OMPL | SBPL |
|------|------|------|
| 规划类型 | 基于采样 | 基于搜索 |
| 完备性 | 概率完备 | 分辨率完备 |
| 最优性 | 渐近最优（RRT*） | 有界次优 |
| 高维效率 | ✅ 优秀 | ⚠️ 随维度指数增长 |
| 确定性 | ❌ 随机 | ✅ 确定 |
| 增量规划 | ❌ 不支持 | ✅ 支持 |
| Anytime | ⚠️ 部分支持 | ✅ 原生支持 |

## 选择指南

### 选择 OMPL 如果：
- 规划空间维度高（≥6 维）
- 不需要严格的最优性保证
- 需要丰富的算法选择
- 与 MoveIt! 集成使用
- 研究新的规划算法

### 选择 SBPL 如果：
- 需要最优性或有界次优保证
- 动态环境需要增量重规划
- Anytime 规划能力重要
- 移动机器人导航场景
- 状态空间可以有效离散化

## 快速开始

### OMPL 安装

```bash
# ROS 集成
sudo apt install ros-noetic-ompl

# 源码安装
git clone https://github.com/ompl/ompl.git
cd ompl && mkdir build && cd build
cmake .. && make -j
```

### SBPL 安装

```bash
# ROS 集成
sudo apt install ros-noetic-sbpl

# 源码安装
git clone https://github.com/sbpl/sbpl.git
cd sbpl && mkdir build && cd build
cmake .. && make -j
```

## 相关资源

- [OMPL 官方文档](https://ompl.kavrakilab.org/)
- [SBPL 官方文档](https://sbpl.net/)
- [OMPL 教程](https://ompl.kavrakilab.org/tutorials.html)
- [SBPL ROS 教程](https://wiki.ros.org/sbpl)
