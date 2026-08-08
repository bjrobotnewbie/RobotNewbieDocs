# clifford (DevonMorris)

**Python Clifford代数计算库，早期的几何代数Python实现。**

## 项目链接

- GitHub: https://github.com/DevonMorris/clifford

## 项目简介

clifford 是一个老牌的 Python 库，用于处理 Clifford 代数（几何代数的数学基础）中的计算。它提供了对多向量（multivectors）的基本运算支持，是 Python 生态中较早的几何代数计算库。

> 注意：这个项目现在已经由 [pygae/clifford](../pygae-clifford/README) 组织接手维护，建议新项目直接使用 pygae 版本。

## 主要功能

### 1. **多向量基本运算**
   - 几何乘积、外积、内积
   - 逆运算、反转运算
   - 等级选择和投影

### 2. **不同度量支持**
   - 可以自定义度量 signature
   - 支持欧氏度量
   - 支持共形几何代数所需的度量

### 3. **Numpy 集成**
   - 底层基于 Numpy 数组存储
   - 可以和其他 Python 科学计算库互操作

### 4. **基本几何构造**
   - 点、线、面、圆、球在 CGA 中的构造
   - 相交、距离计算

## 代码示例

```python
import clifford as cf

# 创建 3D 共形几何代数空间
layout, blades = cf.cl(3, 1)
# 提取基刀片
e1, e2, e3, e4 = blades['e1'], blades['e2'], blades['e3'], blades['e4']

# 创建两个点
p1 = layout.from_point([1, 0, 0])
p2 = layout.from_point([0, 1, 0])

# 计算过两点的圆
circle = p1 ^ p2 ^ einf
```

## 历史背景

- 最早由 Devon Morris 创建
- 后来因为原作者不活跃，项目转移到 [pygae](https://github.com/pygae) 组织下继续开发
- 现在这个仓库主要保留作为历史参考

## 和 pygae/clifford 的关系

| 特性 | DevonMorris/clifford | pygae/clifford |
|------|----------------------|----------------|
| 维护状态 | 停止维护 | 活跃维护 |
| 功能 | 基础功能 | 更多功能，文档更完善 |
| Python支持 | Python 2/3 早期版本 | Python 3.6+ |
| 推荐使用 | 不推荐 | ✅ 推荐 |

## 在机器人学中的用途

- **学习实验**：在 Python 环境中实验共形几何代数算法
- **原型开发**：小规模问题快速验证思路
- **教学**：配合 Jupyter Notebook 做教学演示

## 安装

```bash
pip install clifford
```

> 注意：PyPI 上的 clifford 包现在已经是 pygae 维护的版本。

## 项目状态

- ⭐ Star: ~100+
- 🧑💻 原作者: [Devon Morris](https://github.com/DevonMorris)
- 📅 当前状态：停止维护，代码已合并到 pygae/clifford

## 总结

DevonMorris/clifford 是 Python 几何代数计算的先行者，开创了 Python 中使用几何代数的先河。但现在开发已经转移到 pygae 组织，**新项目推荐直接使用 [pygae/clifford](../pygae-clifford/README)**。
