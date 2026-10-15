# 平移齐次坐标变换
平移齐次坐标变换是**用4×4齐次矩阵表示3维空间平移操作**的数学工具，核心是将3维直角坐标中“非线性的平移”转化为4维齐次空间中“线性的矩阵乘法”，从而统一旋转、平移等变换形式。

## 1 数学表达
**变换对象**：针对3维点的齐次坐标$\widetilde{\boldsymbol{p}} = \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix}$（末尾维度固定为1，区分点与方向向量）。

**核心矩阵**：若点沿x、y、z轴分别平移$t_x$、$t_y$、$t_z$，对应的平移齐次矩阵为：  
$$
 {}^A T_B = \begin{bmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{bmatrix} 
$$
矩阵左上角3×3为单位矩阵（无旋转/缩放），右上角3×1为平移分量（存储平移量），最后一行为固定的[0,0,0,1]。

**变换过程**：通过矩阵乘法完成平移，即$\widetilde{\boldsymbol{p}}' = {}^A T_B \cdot \widetilde{\boldsymbol{p}}$，展开后对应3维直角坐标的平移$\begin{bmatrix} x' \\ y' \\ z' \end{bmatrix} = \begin{bmatrix} x + t_x \\ y + t_y \\ z + t_z \end{bmatrix}$。

## 2 平移齐次坐标变换具体数值案例演
以 “3 维点$\boldsymbol{p} = (2, 3, 4)$沿 x 轴平移$t_x=5$、y 轴平移$t_y=2$、z 轴平移$t_z=0$” 为例，完整计算过程如下：

### 2.1 步骤 1：将 3 维直角坐标转为 4 维齐次坐标
点的齐次坐标末尾固定为 1，因此：$\widetilde{\boldsymbol{p}} = \begin{bmatrix} x \\ y \\ z \\ 1 \end{bmatrix} = \begin{bmatrix} 2 \\ 3 \\ 4 \\ 1 \end{bmatrix}$

### 2.2 步骤 2：构建平移齐次矩阵
根据平移量$t_x=5$、$t_y=2$、$t_z=0$，代入平移齐次矩阵公式（左上角 3×3 为单位矩阵，右上角为平移分量）：${}^A T_B = \begin{bmatrix} 1 & 0 & 0 & t_x \\ 0 & 1 & 0 & t_y \\ 0 & 0 & 1 & t_z \\ 0 & 0 & 0 & 1 \end{bmatrix} = \begin{bmatrix} 1 & 0 & 0 & 5 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix}$

### 2.3 步骤 3：执行齐次变换（矩阵乘法）
按 “4×4 矩阵 × 4×1 向量” 规则计算，结果为变换后的齐次坐标$\widetilde{\boldsymbol{p}}'$：$\widetilde{\boldsymbol{p}}' = {}^A T_B \cdot \widetilde{\boldsymbol{p}} = \begin{bmatrix} 1 & 0 & 0 & 5 \\ 0 & 1 & 0 & 2 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1 \end{bmatrix} \cdot \begin{bmatrix} 2 \\ 3 \\ 4 \\ 1 \end{bmatrix}$

计算每一行结果（第 i 行 = 矩阵第 i 行元素与向量对应元素相乘后求和）：

+ 第 1 行：1×2+0×3+0×4+5×1=2+0+0+5=7
+ 第 2 行：0×2+1×3+0×4+2×1=0+3+0+2=5
+ 第 3 行：0×2+0×3+1×4+0×1=0+0+4+0=4
+ 第 4 行：0×2+0×3+0×4+1×1=1

最终得到：$\widetilde{\boldsymbol{p}}' = \begin{bmatrix} 7 \\ 5 \\ 4 \\ 1 \end{bmatrix}$

### 2.4 步骤 4：将齐次坐标转回直角坐标
忽略齐次坐标末尾的 1，提取前 3 个分量即为平移后的直角坐标：$\boldsymbol{p}' = (7, 5, 4)$

### 2.5 步骤 5：结果验证
对比原始点$(2,3,4)$与结果$(7,5,4)$，x 轴增加 5、y 轴增加 2、z 轴不变，完全符合预设平移量，验证变换正确。

