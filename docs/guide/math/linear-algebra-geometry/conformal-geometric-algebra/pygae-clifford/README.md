# pygae/clifford

**Python 生态中最活跃的几何代数库，开源社区维护。**

## 项目链接

- GitHub: https://github.com/pygae/clifford

## 项目简介

pygae/clifford 是 Python 中最成熟的几何代数计算库，它继承自早期的 DevonMorris/clifford，现在由 Pygae（Pythonic Geometric Algebra Enthusiasts）社区团队继续维护开发。

对于大多数 Python 用户，这是**推荐首选**。

## 主要特点

### 1. **功能完整**
   - 完整的多代数运算：几何乘积、外积、左缩、右缩、共轭...
   - 支持任意维度和度量
   - 共形几何代数(CGA)开箱即用
   - 投影几何代数(PGA)支持

### 2. **Python 生态友好**
   - 深度集成 Numpy, Scipy
   - 配合 Matplotlib 可视化
   - 可以和 Jupyter Notebook 完美配合
   - 适合交互式探索和快速原型

### 3. **文档完善**
   - 详细的 API 文档
   - 大量示例 Notebook
   - 入门教程齐全
   - 活跃的社区问答

### 4. **持续更新**
   - 社区团队维护
   - 积极处理 Issue 和 PR
   - 跟进 Python 版本更新

## 代码示例

```python
import clifford as cf
import numpy as np

# 创建 3D 共形几何代数空间
layout, blades = cf.conformalize(cf.Cl(3))
print(f'维度: {layout.n_dim}')

# 提取常用刀片
e1, e2, e3 = blades.e1, blades.e2, blades.e3
einf = blades.einf
eo = blades.eo

# 从欧氏坐标创建共形点
def point(x, y, z):
    return eo + x*e1 + y*e2 + z*e3 + 0.5*(x*x + y*y + z*z)*einf

p1 = point(1, 0, 0)
p2 = point(0, 1, 0)
p3 = point(0, 0, 1)

# 计算过三点的圆
circle = p1 ^ p2 ^ p3
print(f'圆: {circle}')
```

## 安装

```bash
# 使用 pip
pip install clifford

# 从源码安装最新版本
pip install git+https://github.com/pygae/clifford.git
```

## 在机器人学中的用途

### 适合场景

- **算法研发**：在 Python 中快速验证共形几何代数算法
- **教学实验**：配合 Jupyter Notebook，一步一步演示计算过程
- **数据处理**：结合 Python 数据科学生态处理几何数据
- **离线标定**：手眼标定、相机标定等离线计算任务

### 不适合场景

- **实时控制**：Python 性能不如 C++/Rust
- **嵌入式部署**：需要转到编译型语言

## 学习资源

- [官方文档](https://clifford.readthedocs.io/)
- [示例 Notebooks](https://github.com/pygae/clifford/tree/master/examples)
- [Gitter 聊天室](https://gitter.im/pygae/clifford) 社区交流

## 和 DevonMorris/clifford 的关系

- 这是 DevonMorris/clifford 的**官方继任者**
- 原作者不再维护，社区接手继续开发
- API 基本兼容，修复了大量 bug，增加了很多新功能
- **新项目强烈推荐使用这个版本**

## 项目状态

- ⭐ Star: ~800+
- 🧑💻 维护: Pygae 社区团队
- 📅 状态：**活跃维护，持续更新**
- 🐍 Python 版本: 3.7+

## 对比

| 特性 | pygae/clifford | 其他 Python 库 |
|------|----------------|---------------|
| 功能完整 | ✅ | ⚠️ 功能较少 |
| 文档质量 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| 社区活跃 | ✅ | ⚠️ 不活跃 |
| 易用性 | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ |
| 性能 | ⭐⭐⭐ | ⭐⭐⭐ (编译型更快) |

## 总结

pygae/clifford 是**Python 学习和使用共形几何代数的首选**。无论你是初学者做实验，还是研究者快速验证算法，pygae/clifford 都能满足你的需求。文档完善，社区活跃，推荐从这里开始你的 CGA Python 之旅。
