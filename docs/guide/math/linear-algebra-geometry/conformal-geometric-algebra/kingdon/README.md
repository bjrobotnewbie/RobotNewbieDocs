# kingdon

**Rust 高性能几何代数库，追求极致性能。**

## 项目链接

- GitHub: https://github.com/tBuLi/kingdon

## 项目简介

kingdon 是一个用 Rust 编写的现代几何代数库，专注于高性能计算。它利用 Rust 的类型系统和零成本抽象，在保持代码简洁的同时，提供接近手工优化 C 的性能。

对于机器人学这类需要实时计算的场景，kingdon 是一个很好的选择。

## 主要特点

### 1. **Rust 原生实现**
   - 零成本抽象，运行时开销极小
   - 内存安全，无 GC 停顿
   - 适合嵌入式和实时系统

### 2. **编译时优化**
   - 使用 Rust 泛型在编译期确定代数维度
   - 大量使用 const 泛型
   - 编译器可以做激进的内联和优化

### 3. **支持多种几何代数**
   - Conformal Geometric Algebra (CGA)
   - Projective Geometric Algebra (PGA)
   - Euclidean Geometric Algebra (EGA)
   - 可以自定义 metric

### 4. **通用多向量表示**
   - 稀疏存储：只存储非零分量
   - 对于稀疏多向量更节省内存
   - 适合机器人学中多数运算

## 代码示例

```rust
use kingdon::prelude::*;

// 3D Conformal Geometric Algebra
type CGA3 = Conformal<f64, 3>;
let cga = CGA3::new();

// 创建点
let p1 = cga.point(1.0, 0.0, 0.0);
let p2 = cga.point(0.0, 1.0, 0.0);
let p3 = cga.point(0.0, 0.0, 1.0);

// 计算过三点的圆
let circle = p1.op(p2).op(p3);
```

## 在机器人学中的优势

| 场景 | kingdon 优势 |
|------|-------------|
| **实时逆运动学** | Rust + 编译期优化，延迟极低 |
| **高频碰撞检测** | 每秒可以进行成千上万次碰撞检测 |
| **机器人关节控制** | 可以在嵌入式MCU上运行（Rust支持no_std） |
| **高性能仿真** | 大规模多机器人仿真更流畅 |

## no_std 支持

kingdon 支持 `no_std` 环境，意味着可以直接在：
- 嵌入式机器人控制器
- 自动驾驶车载计算单元
- FPGA 软核处理器

上运行，不需要操作系统支持。

## 依赖

```toml
# Cargo.toml
kingdon = "0.1"
```

## 项目状态

- ⭐ Star: ~100+
- 🧑💻 作者: [tBuLi](https://github.com/tBuLi)
- 📅 状态：活跃开发中
- 🦀 Rust 版本: 1.60+

## 对比其他库

| 库 | 语言 | 性能 | 易用性 | 生产环境 |
|---|------|------|--------|----------|
| kingdon | Rust | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ✅ 可用 |
| pygae/clifford | Python | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | 原型 |
| gafro | C++ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ✅ 可用 |
| ganja.js | JS | ⭐⭐ | ⭐⭐⭐⭐⭐ | 演示 |

## 总结

kingdon 是**高性能几何代数计算的现代选择**，如果你在用 Rust 开发机器人，或者需要在嵌入式/实时场景使用共形几何代数，kingdon 值得一试。
