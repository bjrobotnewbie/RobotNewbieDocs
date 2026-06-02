# Numerical Optimization

## 资源简介

Numerical Optimization 是由 Jorge Nocedal 和 Stephen J. Wright 合著的数值优化经典教材，系统讲解了各类优化算法的原理和实现。这本书在工业界和学术界都被广泛使用，是机器人运动规划、控制、状态估计等领域优化问题的重要参考书。

## 官方链接

- 本书主页（Northwestern University）：<https://users.iems.northwestern.edu/~nocedal/book/>
- GitHub 算法实现：<https://github.com/eigenvivek/Numerical-Optimization>
- Amazon 购买页面：<https://www.amazon.com/Numerical-Optimization-Second-Jorge-Nocedal/dp/0387403213>

## 核心内容

- 线性规划与整数规划
- 无约束优化：线搜索方法、牛顿法、拟牛顿法（BFGS、L-BFGS）
- 约束优化：拉格朗日乘子法、二次规划、内点法
- 非线性最小二乘：高斯-牛顿法、Levenberg-Marquardt算法
- 共轭梯度法
- 信赖域方法
- 全局优化简介

## 适用场景与学习人群

- 机器人学：运动规划、轨迹优化、参数校准
- 计算机视觉：捆绑调整（BA）、SLAM优化
- 机器学习：模型参数拟合、深度学习优化
- 控制理论：模型预测控制（MPC）
- 应用数学方向研究生和研究者

## 特色优势

- 理论严谨，算法讲解清晰
- 包含大量算法伪代码和实现细节
- 强调算法的实际应用和性能分析
- 第二版更新了共轭梯度、内点法等现代方法

## 学习建议

- 机器人学中重点学习非线性最小二乘（高斯-牛顿法、LM算法），用于状态估计和校准
- 拟牛顿法和共轭梯度法在大规模优化问题中非常重要
- 阅读算法伪代码，理解迭代过程和停止条件
- 结合Ceres Solver、G2O等库理解实际应用
