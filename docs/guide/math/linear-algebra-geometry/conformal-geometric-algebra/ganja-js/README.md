# ganja.js

**浏览器端交互式几何代数可视化，让几何代数变得可交互可直观。**

## 项目链接

- GitHub: https://github.com/enkimute/ganja.js

## 项目简介

ganja.js 是一个轻量级的 JavaScript 几何代数库，专门用于在浏览器中进行几何代数计算和交互式可视化。它最大的特点是**开箱即用**，只需几行代码就能创建交互式的几何代数演示。

## 主要特点

### 1. **零配置，直接用**
   - 只需引入一个 JS 文件，无需任何构建工具
   - 支持直接在 HTML 中编写 GA 表达式
   - 适合教学、演示、快速原型验证

### 2. **内置交互式可视化**
   - 自动渲染点、线、面、圆、球等几何实体
   - 支持 3D 交互旋转缩放
   - 实时更新，拖拽修改参数立即看到结果

### 3. **支持多种几何代数**
   - 2D Conformal Geometric Algebra (CGA)
   - 3D Conformal Geometric Algebra (CGA)
   - Projective Geometric Algebra (PGA)
   - 可以自定义 signature

### 4. **简洁的 API 设计**
```javascript
// 创建点
let p1 = 1e0 + 0.5*1e1 + 2*1e2 + (0.5*0.5+2*2)*1e3;
// 创建圆
let circle = p1 ^ p2 ^ p3;
// 可视化
Element.renderCanvas();
```

## 在机器人学中的用途

### 适合场景
- **教学演示**：讲解共形几何代数基本概念，交互展示几何实体
- **算法验证**：快速原型验证CGA算法，比如逆运动学解法
- **可视化调试**：调试碰撞检测算法，直观看到距离计算结果
- **线上教程**：创建交互式教程，让读者动手实验

### 不适合场景
- 大规模生产环境计算（JavaScript性能有限）
- 机器人实时控制（需要更低延迟）

## 示例项目

ganja.js 官网提供了很多示例：
- 基本几何实体构造（点、线、圆、平面、球）
- 交点计算（两个圆相交、球面相等等）
- 刚体变换（转子表示）
- 逆运动学示例

## 适用人群

- 初学者：想直观理解几何代数，不需要复杂计算
- 教师：制作教学演示和交互式课件
- 研究者：快速验证几何代数新算法

## 使用方式

```html
<script src="https://cdn.jsdelivr.net/gh/enkimute/ganja.js/ganja.js"></script>
<script>
  // Your geometric algebra code here
</script>
```

## 项目状态

- ⭐ Star: ~1.5k+
- 🧑💻 主要维护者: [enkimute](https://github.com/enkimute)
- 📅 最后更新：活跃维护中

## 总结

ganja.js 是**学习共形几何代数的最佳入门工具**，它让抽象的几何代数概念变得看得见、摸得着、可交互。推荐从 ganja.js 开始你的 CGA 学习之旅。
