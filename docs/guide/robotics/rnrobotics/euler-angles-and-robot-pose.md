# 欧拉角与机器人姿态表示
在机器人学中，姿态（Orientation）描述了刚体在空间中的朝向，是运动学、动力学分析及控制的核心基础。欧拉角作为最早用于表示三维姿态的数学工具之一，通过将复杂的三维旋转分解为绕三个正交轴的连续单轴旋转，实现了姿态的直观量化。但欧拉角的旋转轴选择存在 “内旋” 与 “外旋” 两种核心逻辑，这是理解其数学建模与工程应用的关键前提。本章将系统讲解欧拉角的定义、内旋 / 外旋逻辑、旋转顺序、数学建模、局限性及典型应用，为后续机器人运动学求解奠定基础。

## 1 欧拉角的基本定义与核心逻辑：内旋与外旋
### 1.1 核心概念：从二维到三维的旋转扩展
在二维平面中，刚体的旋转仅需一个角度即可描述（如绕垂直于平面的 z 轴旋转 θ 角）；但在三维空间中，刚体的姿态无法通过单一角度确定 —— 根据刚体运动学原理，任意三维旋转都可等效为绕三个两两正交的轴的连续单轴旋转，这三个用于描述旋转的角度即为 “欧拉角（Euler Angles）”。

欧拉角的物理意义在于 “分解与直观”：每个角度对应一个明确的 “单轴旋转动作”，但旋转轴的选择存在两种截然不同的逻辑 —— 内旋与外旋，这直接决定了旋转过程的数学建模方式。

### 1.2 关键前提：内旋（Intrinsic Rotation）与外旋（Extrinsic Rotation）
欧拉角的本质差异源于 “旋转轴是否随刚体同步运动”，需结合固定坐标系与随体坐标系的定义区分：

+ 固定坐标系（惯性系，如机器人基座坐标系 {A}）：轴的方向固定不变，不随刚体运动而改变；
+ 随体坐标系（刚体坐标系，如机器人末端执行器坐标系 {E}）：与刚体固连，轴的方向随刚体姿态变化而同步更新。

基于两种坐标系，欧拉角的旋转逻辑分为两类：

#### 1.2.1 外旋（绕固定轴旋转）
+ 核心规则：所有旋转轴均为固定坐标系 {A} 的 x/y/z 轴，轴的方向始终不变，与刚体姿态无关。当三个旋转轴互不相同时（如 Z-Y-X），这类欧拉角也称为 Tait–Bryan 角或卡尔丹角（Cardan Angles），常用于航空航天和机器人学。
+ 旋转过程示例（Z-Y-X 外旋）：
1. 第一步：绕固定坐标系 {A} 的 Z 轴转 α 角；
2. 第二步：绕固定坐标系 {A} 的 Y 轴转 β 角（轴仍为 {A} 的 Y 轴，不随第一步旋转偏移）；
3. 第三步：绕固定坐标系 {A} 的 X 轴转 γ 角（轴仍为 {A} 的 X 轴，不随前两步旋转偏移）。
+ 特点：轴的方向固定，数学建模简单，但与刚体 “随动旋转” 的物理直觉不符，多用于需要固定地面参考的场景（如移动机器人航向角计算）。

#### 1.2.2 内旋（绕随体轴旋转）
+ 核心规则：所有旋转轴均为随体坐标系 {E} 的 x/y/z 轴，前一次旋转后，后续旋转轴随随体坐标系同步偏移。在机器人学中，内旋逻辑因贴合刚体运动直觉而被广泛采用，常被称为“欧拉角表示”，尽管严格来说，欧拉原始定义使用的是重复轴序列（如 Z-X-Z）。
+ 旋转过程示例（Z-Y-X 内旋）：
1. 第一步：绕初始随体坐标系 {E0} 的 Z 轴转 α 角（{E0} 与 {A} 重合，轴为 {E0} 的 Z 轴，即 {A} 的 Z 轴）；
2. 第二步：绕第一步旋转后的随体坐标系 {E1} 的 Y 轴转 β 角（轴为 {E1} 的 Y 轴，已随第一步旋转偏移，非 {A} 的 Y 轴）；
3. 第三步：绕第二步旋转后的随体坐标系 {E2} 的 X 轴转 γ 角（轴为 {E2} 的 X 轴，已随前两步旋转偏移，非 {A} 的 X 轴）。
+ 特点：轴的方向随刚体同步更新，贴合刚体运动的物理直觉，是机器人学中描述机械臂末端、关节旋转的主流逻辑（如 6 轴机械臂的姿态控制）。

无论内旋还是外旋，旋转顺序必须明确声明—— 不同顺序（如 X-Y-Z、Z-Y-X）对应的姿态结果完全不同，这是欧拉角使用中最易出错的关键点。

## 2 欧拉角的旋转顺序与数学建模（内旋为核心）
在机器人学中，内旋因贴合刚体运动逻辑应用更广泛，以下以工业机器人常用的内旋顺序为例，讲解其数学建模过程。

### 2.1 机器人学中常用的内旋顺序
#### 2.1.1 Z-Y-X 内旋顺序（航空航天 / 机械臂常用）
Z-Y-X 内旋顺序（又称 “滚转 - 俯仰 - 偏航”，Roll-Pitch-Yaw）是 6 轴串联机械臂末端姿态描述的主流选择，其旋转过程（基于内旋逻辑）为：

1. 第一步（偏航，Yaw）：绕初始随体坐标系 {E0} 的 Z 轴旋转 α 角 ——{E0} 与固定坐标系 {A} 重合，旋转后得到随体坐标系 {E1}，{E1} 的 Z 轴与 {E0} 的 Z 轴一致（因绕自身 Z 轴旋转），X/Y 轴随旋转偏移；
2. 第二步（俯仰，Pitch）：绕 {E1} 的 Y 轴旋转 β 角 —— 旋转轴为 {E1} 的 Y 轴（已随第一步偏移），旋转后得到 {E2}，{E2} 的 Y 轴与 {E1} 的 Y 轴一致，X/Z 轴随旋转偏移；
3. 第三步（滚转，Roll）：绕 {E2} 的 X 轴旋转 γ 角 —— 旋转轴为 {E2} 的 X 轴（已随前两步偏移），旋转后得到最终随体坐标系 {E}，{E} 的 X 轴与 {E2} 的 X 轴一致，Y/Z 轴随旋转偏移。

#### 2.1.2 X-Y-Z 内旋顺序（移动机器人 / 相机姿态常用）
X-Y-Z 内旋顺序更适配移动机器人（如 AGV）的运动逻辑，其旋转过程为：

1. 第一步（滚转，Roll）：绕初始随体坐标系 {E0} 的 X 轴旋转 α 角（X 轴沿机器人前进方向）；
2. 第二步（俯仰，Pitch）：绕 {E1} 的 Y 轴旋转 β 角（Y 轴水平向左）；
3. 第三步（偏航，Yaw）：绕 {E2} 的 Z 轴旋转 γ 角（Z 轴垂直向上）。

该顺序中，角度直接对应机器人的运动状态：Yaw 角控制左右转向，Pitch 角反映坡道倾斜，Roll 角检测侧翻风险，直观且易于控制。

### 2.2 欧拉角的旋转矩阵建模（内旋逻辑）
欧拉角的核心价值在于 “可通过单轴旋转矩阵的乘积，推导姿态对应的旋转矩阵”—— 这是机器人正运动学中 “从关节角计算末端姿态” 的关键步骤。

#### 2.2.1 单轴旋转矩阵回顾
在右手坐标系下，绕随体坐标系 x、y、z 轴旋转 θ 角的基本旋转矩阵（逆时针为正方向）如下（内旋与外旋的单轴矩阵形式一致，差异仅在于轴的归属）：

+ 绕 x 轴旋转矩阵：$R_x(\theta) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \cos\theta & -\sin\theta \\ 0 & \sin\theta & \cos\theta \end{bmatrix}$
+ 绕 y 轴旋转矩阵：$R_y(\theta) = \begin{bmatrix} \cos\theta & 0 & \sin\theta \\ 0 & 1 & 0 \\ -\sin\theta & 0 & \cos\theta \end{bmatrix}$（sinθ 符号与 x、z 轴相反，由右手定则决定）
+ 绕 z 轴旋转矩阵：$R_z(\theta) = \begin{bmatrix} \cos\theta & -\sin\theta & 0 \\ \sin\theta & \cos\theta & 0 \\ 0 & 0 & 1 \end{bmatrix}$

#### 2.2.2 Z-Y-X 内旋顺序的旋转矩阵推导
以 Z-Y-X 内旋顺序（α：绕随体 Z 轴，β：绕随体 Y 轴，γ：绕随体 X 轴）为例，推导随体坐标系 {E} 相对于固定坐标系 {A} 的姿态旋转矩阵$^A R_E$。

由于内旋是在当前随体坐标系中进行的，每次新旋转相当于在当前姿态基础上**左乘**对应的旋转矩阵，因此矩阵乘法顺序与旋转执行顺序一致，具体推导过程如下：

1. 第一步：绕 {E0} 的 Z 轴转 α 角，初始随体坐标系 {E0} 与 {A} 重合，旋转矩阵为$R_z(\alpha)$，此时 {E1} 相对于 {A} 的旋转矩阵为$R_z(\alpha)$；
2. 第二步：绕 {E1} 的 Y 轴转 β 角，旋转矩阵$R_y(\beta)$需基于第一步的姿态左乘$R_z(\alpha)$，故复合矩阵为$R_z(\alpha) \cdot R_y(\beta)$；
3. 第三步：绕 {E2} 的 X 轴转 γ 角，旋转矩阵$R_x(\gamma)$需基于前两步的姿态左乘$R_z(\alpha) \cdot R_y(\beta)$，故复合矩阵为$R_z(\alpha) \cdot R_y(\beta) \cdot R_x(\gamma)$。

最终，Z-Y-X 内旋顺序欧拉角（α, β, γ）对应的姿态旋转矩阵为：  
$$
 ^A R_E = R_z(\alpha) \cdot R_y(\beta) \cdot R_x(\gamma) 
$$

其中，$^A R_E$ 表示将**随体坐标系中的向量**转换到**固定坐标系**，即满足 $\mathbf{v}_A = {}^A R_E \cdot \mathbf{v}_E$，$\mathbf{v}_A$ 为向量在固定坐标系 {A} 中的表示，$\mathbf{v}_E$ 为向量在随体坐标系 {E} 中的表示。

将基本旋转矩阵代入并利用$\cos^2\theta + \sin^2\theta = 1$化简，展开式为：  
$$
^A R_E = \begin{bmatrix}
\cos\alpha\cos\beta & \cos\alpha\sin\beta\sin\gamma - \sin\alpha\cos\gamma & \cos\alpha\sin\beta\cos\gamma + \sin\alpha\sin\gamma \\
\sin\alpha\cos\beta & \sin\alpha\sin\beta\sin\gamma + \cos\alpha\cos\gamma & \sin\alpha\sin\beta\cos\gamma - \cos\alpha\sin\gamma \\
-\sin\beta & \cos\beta\sin\gamma & \cos\beta\cos\gamma
\end{bmatrix}
$$

该矩阵与从固定坐标系视角看，按 X-Y-Z 顺序进行外旋得到的结果矩阵完全相同。一般地，任意内旋序列 $R_{a}(\alpha) R_{b}(\beta) R_{c}(\gamma)$ 等价于反序的外旋序列 $R_{c}(\gamma) R_{b}(\beta) R_{a}(\alpha)$，这体现了内旋与外旋在特定条件下的等价性。

#### 2.2.3 内旋与外旋的矩阵乘法顺序差异
+ 内旋：旋转顺序与矩阵乘法顺序一致（如 Z-Y-X 内旋对应$R_z \cdot R_y \cdot R_x$）—— 因后一次旋转的轴随前一次旋转偏移，每次新的旋转（对应的矩阵）需左乘到当前累积的变换矩阵上，相当于在当前随体坐标系中施加旋转。
+ 外旋：旋转顺序与矩阵乘法顺序相反（如 Z-Y-X 外旋对应$R_x \cdot R_y \cdot R_z$）—— 因所有轴均为固定轴，每次新的旋转（对应的矩阵）需右乘到当前累积的变换矩阵上，相当于在原始固定坐标系中施加旋转。

这一差异是内旋与外旋数学建模的核心区别，需严格区分以避免姿态计算错误。

## 3 欧拉角的逆问题：从旋转矩阵求欧拉角
在机器人逆运动学中，常需 “已知末端姿态旋转矩阵$^A R_E$，反求对应的欧拉角”—— 这一过程称为欧拉角的 “逆解”。由于三角函数的周期性（如$\cos\theta = \cos(-\theta)$，$\sin\theta = -\sin(-\theta)$），逆解可能存在多组（需结合机器人运动范围筛选合理解）。

以下以 Z-Y-X 内旋顺序为例，推导逆解过程：

### 3.1 提取关键角度（β≠±π/2 时）
设$^A R_E = \begin{bmatrix} r_{11} & r_{12} & r_{13} \\ r_{21} & r_{22} & r_{23} \\ r_{31} & r_{32} & r_{33} \end{bmatrix}$，与 Z-Y-X 内旋的旋转矩阵展开式对比：

1. 求俯仰角 β：从$r_{31} = -\sin\beta$，可得$\beta = -\arcsin(r_{31})$。注：$\arcsin$的取值范围是$[-\pi/2, \pi/2]$，若需覆盖$\pi/2 \sim 3\pi/2$，需结合$r_{11}^2 + r_{21}^2 = \cos^2\beta$判断（若$\cos\beta < 0$，则$\beta = \pi + \arcsin(r_{31})$）。
2. 求偏航角 α：当$\cos\beta \neq 0$时，从$r_{21} = \sin\alpha\cos\beta$和$r_{11} = \cos\alpha\cos\beta$，可得$\tan\alpha = \frac{r_{21}}{r_{11}}$，即$\alpha = \arctan2(r_{21}, r_{11})$（$\arctan2$可自动判断 α 所在象限，取值范围$[-\pi, \pi]$）。
3. 求滚转角 γ：同理，从$r_{32} = \cos\beta\sin\gamma$和$r_{33} = \cos\beta\cos\gamma$，可得$\tan\gamma = \frac{r_{32}}{r_{33}}$，即$\gamma = \arctan2(r_{32}, r_{33})$。

### 3.2 特殊情况：β=±π/2 时的逆解（万向节死锁）
当$\beta = \pi/2$（或$-\pi/2$）时，$\cos\beta = 0$，此时旋转矩阵中的$r_{11} = r_{21} = 0$，$\tan\alpha$无意义 —— 这正是 “万向节死锁” 场景。其中，当 β = +90° 时，姿态仅依赖于 $\alpha - \gamma$；当 β = -90° 时，姿态仅依赖于 $\alpha + \gamma$，即 α 与 γ 无法单独确定，仅能得到角度组合值，需结合机器人关节角范围（如机械臂关节限位）确定其中一个角度，再求解另一个。

## 4 欧拉角的局限性：万向节死锁（内旋逻辑下的本质）
在机器人学常用的 Z-Y-X 内旋顺序中（绕随体 Z 轴→绕随体 Y 轴→绕随体 X 轴），当中间旋转轴（随体 Y 轴）的旋转角度 β=±90° 时，会出现 “旋转矩阵退化” 现象 —— 原本描述三维旋转的独立参数失去独立性，导致刚体丢失一个旋转自由度，这就是万向节死锁的本质。以下从数学推导角度完整解析这一过程。

### 4.1 内旋逻辑下 Z-Y-X 顺序的旋转矩阵构建
内旋的核心特征是 “后一次旋转的轴随前一次旋转同步更新”，因此 Z-Y-X 内旋顺序的姿态旋转矩阵，需通过 “前一次旋转矩阵左乘后一次旋转矩阵” 的方式构建（矩阵乘法顺序与旋转顺序一致）。

#### 4.1.1 单轴旋转矩阵基础
在右手坐标系下，绕随体 X、Y、Z 轴旋转 θ 角的标准旋转矩阵分别为（逆时针为正方向）：

+ 绕随体 X 轴旋转 θ 角：$R_x(\theta) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \cos\theta & -\sin\theta \\ 0 & \sin\theta & \cos\theta \end{bmatrix}$（仅改变 Y、Z 轴方向，X 轴为旋转轴，方向不变）
+ 绕随体 Y 轴旋转 θ 角：$R_y(\theta) = \begin{bmatrix} \cos\theta & 0 & \sin\theta \\ 0 & 1 & 0 \\ -\sin\theta & 0 & \cos\theta \end{bmatrix}$（仅改变 X、Z 轴方向，Y 轴为旋转轴，方向不变，注意 sinθ 符号与 X/Z 轴旋转矩阵相反）
+ 绕随体 Z 轴旋转 θ 角：$R_z(\theta) = \begin{bmatrix} \cos\theta & -\sin\theta & 0 \\ \sin\theta & \cos\theta & 0 \\ 0 & 0 & 1 \end{bmatrix}$（仅改变 X、Y 轴方向，Z 轴为旋转轴，方向不变）

#### 4.1.2 Z-Y-X 内旋的复合旋转矩阵
Z-Y-X 内旋顺序的完整过程为：

1. 第一步：绕初始随体 Z 轴（与固定 Z 轴重合）旋转 α 角，旋转矩阵为$R_z(\alpha)$；
2. 第二步：绕第一步旋转后的随体 Y 轴旋转 β 角，旋转矩阵为$R_y(\beta)$（需基于第一步的姿态，故左乘$R_z(\alpha)$）；
3. 第三步：绕第二步旋转后的随体 X 轴旋转 γ 角，旋转矩阵为$R_x(\gamma)$（需基于前两步的姿态，故左乘$R_z(\alpha)R_y(\beta)$）。

因此，随体坐标系 {E} 相对于固定坐标系 {A} 的复合旋转矩阵为：  
$$
 ^A R_E = R_z(\alpha) \cdot R_y(\beta) \cdot R_x(\gamma) \tag{4.1} 
$$

将单轴旋转矩阵代入式 (4.1)，展开并利用$\cos^2\theta + \sin^2\theta = 1$化简，最终得到：  
$$
^A R_E = \begin{bmatrix}
\cos\alpha\cos\beta & \cos\alpha\sin\beta\sin\gamma - \sin\alpha\cos\gamma & \cos\alpha\sin\beta\cos\gamma + \sin\alpha\sin\gamma \\
\sin\alpha\cos\beta & \sin\alpha\sin\beta\sin\gamma + \cos\alpha\cos\gamma & \sin\alpha\sin\beta\cos\gamma - \cos\alpha\sin\gamma \\
-\sin\beta & \cos\beta\sin\gamma & \cos\beta\cos\gamma
\end{bmatrix} \tag{4.2}
$$

式 (4.2) 是描述 Z-Y-X 内旋姿态的核心表达式，正常情况下（β≠±90°），矩阵中各元素可通过 α、β、γ 三个独立参数唯一确定，对应三维空间的一个姿态。

### 4.2 万向节死锁的数学本质：β = ±90° 时的旋转矩阵退化
在 Z-Y-X 内旋顺序（即：先绕随体 Z 轴旋转偏航角 $\alpha$，再绕新 Y 轴旋转俯仰角 $\beta$，最后绕新 X 轴旋转滚转角 $\gamma$）下，随体坐标系 $\{E\}$ 相对于固定坐标系 $\{A\}$ 的复合旋转矩阵为${}^A R_E = R_z(\alpha) \cdot R_y(\beta) \cdot R_x(\gamma)$。

当中间旋转角 $\beta = 90^\circ$（或 $\beta = -90^\circ$，推导逻辑完全一致）时，$\cos\beta = 0$、$\sin\beta = 1$，代入后旋转矩阵发生结构退化：原本由三个独立参数 $(\alpha, \beta, \gamma)$ 唯一确定的三维姿态，退化为仅依赖组合参数 $(\alpha - \gamma)$（β=90°）或 $(\alpha + \gamma)$（β=-90°）的二维姿态描述。这一退化直接导致系统自由度由 3 降至 2，即发生万向节死锁（Gimbal Lock）。

#### 4.2.1 β = 90° 时的退化旋转矩阵
将 $\beta = 90^\circ$（即 $\cos\beta = 0$，$\sin\beta = 1$）代入式 (4.2)，化简后得到：  
$$
{}^A R_E(\beta = 90^\circ) =
\begin{bmatrix}
0 & \cos\alpha\sin\gamma - \sin\alpha\cos\gamma & \cos\alpha\cos\gamma + \sin\alpha\sin\gamma \\
0 & \sin\alpha\sin\gamma + \cos\alpha\cos\gamma & \sin\alpha\cos\gamma - \cos\alpha\sin\gamma \\
-1 & 0 & 0
\end{bmatrix}
\tag{4.3}
$$

利用三角函数恒等式进一步简化矩阵元素：

+ $\cos\alpha\sin\gamma - \sin\alpha\cos\gamma = -\sin(\alpha - \gamma)$（正弦差公式），
+ $\cos\alpha\cos\gamma + \sin\alpha\sin\gamma = \cos(\alpha - \gamma)$（余弦差公式），
+ $\sin\alpha\sin\gamma + \cos\alpha\cos\gamma = \cos(\alpha - \gamma)$（余弦差公式），
+ $\sin\alpha\cos\gamma - \cos\alpha\sin\gamma = \sin(\alpha - \gamma)$（正弦差公式）。

将上述恒等式代入式 (4.3)，退化旋转矩阵可简化为：  
$$
{}^A R_E(\beta = 90^\circ) =
\begin{bmatrix}
0 & -\sin(\alpha - \gamma) & \cos(\alpha - \gamma) \\
0 & \cos(\alpha - \gamma) & \sin(\alpha - \gamma) \\
-1 & 0 & 0
\end{bmatrix}
\tag{4.4}
$$

#### 4.2.2 旋转矩阵退化的关键特征
旋转矩阵 ${}^A R_E$ 的列向量具有明确的物理意义：分别对应随体坐标系 $\{E\}$ 的 X、Y、Z 轴在固定坐标系 $\{A\}$ 中的方向矢量。由式 (4.4) 可直接提取随体三轴的方向：

+ 随体 X 轴：$\boldsymbol{x}_E = \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}$，
+ 随体 Y 轴：$\boldsymbol{y}_E = \begin{bmatrix} -\sin(\alpha - \gamma) \\ \cos(\alpha - \gamma) \\ 0 \end{bmatrix}$，
+ 随体 Z 轴：$\boldsymbol{z}_E = \begin{bmatrix} \cos(\alpha - \gamma) \\ \sin(\alpha - \gamma) \\ 0 \end{bmatrix}$。

基于上述方向矢量，可得出旋转矩阵退化的两个核心特征：

1. 在 β=±90° 时，随体 X 轴方向被完全固定
    - 随体 X 轴的方向矢量 $\boldsymbol{x}_E = \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}$ 中，所有分量均为常数，与 $\alpha$ 和 $\gamma$ 完全无关；
    - 物理意义：无论如何调整偏航角 $\alpha$（绕随体 Z 轴）或滚转角 $\gamma$（绕随体 X 轴），随体 X 轴的空间指向始终固定（沿固定坐标系 $\{A\}$ 的负 Z 轴方向）。
2. 在 β=±90° 时，偏航角$\alpha$与滚转角$\gamma$完全耦合
    - 随体 Y 轴和 Z 轴的方向矢量中，所有可变元素仅依赖于组合参数 $(\alpha - \gamma)$（β=90°）或 $(\alpha + \gamma)$（β=-90°），而非 $\alpha$ 和 $\gamma$ 单独取值；
    - 示例验证：
        * 情况 A：$\alpha = 30^\circ$，$\gamma = 10^\circ$ → 组合参数 $\alpha - \gamma = 20^\circ$，此时 $\boldsymbol{y}_E = \begin{bmatrix} -\sin20^\circ \\ \cos20^\circ \\ 0 \end{bmatrix}$，$\boldsymbol{z}_E = \begin{bmatrix} \cos20^\circ \\ \sin20^\circ \\ 0 \end{bmatrix}$；
        * 情况 B：$\alpha = 50^\circ$，$\gamma = 30^\circ$ → 组合参数 $\alpha - \gamma = 20^\circ$，此时 $\boldsymbol{y}_E$ 和 $\boldsymbol{z}_E$ 与情况 A 完全相同；
    - 结论：两种不同的 $\alpha$ 和 $\gamma$ 组合，因角度组合值相同，最终对应完全一致的姿态 —— 这表明 $\alpha$ 和 $\gamma$ 不再提供独立的控制自由度，两个参数的作用被 “压缩” 为一个组合参数。

综上，原本的三个欧拉角参数 $(\alpha, \beta, \gamma)$ 中，$\beta = ±90^\circ$ 被固定，$\alpha$ 和 $\gamma$ 耦合为一个有效参数，系统自由度由 3 降至 2，即丢失一个旋转自由度，符合万向节死锁的定义。

#### 4.2.3 万向节死锁的意义
万向节死锁的数学本质并非旋转矩阵 “失效”（退化后的矩阵仍满足正交性，行列式为 +1，仍是合法的旋转矩阵），而是欧拉角参数化在β = ±90°处出现奇异性：

1. 姿态与欧拉角的映射关系不再唯一（多个角度组合对应同一姿态）；
2. 描述微分运动的雅可比矩阵奇异，导致姿态控制的 “不可微性”；
3. 两个旋转轴（初始随体 Z 轴与最终随体 X 轴）在空间中重合，使两个独立角度耦合为单一参数。

### 4.3 万向节死锁的几何本质与解析证明
从几何角度看，欧拉角在俯仰角（$\beta = \pm 90^\circ$）时发生万向节死锁（Gimbal Lock），其本质是：两个旋转轴在空间中重合，导致系统自由度由 3 降至 2。对于 Z-Y-X 内旋顺序（即 Tait-Bryan 角，常用于航空航天），当 $\beta = 90^\circ$ 时，初始的偏航轴（固定系 Z 轴）与最终的滚转轴（随体 X 轴）在空间中对齐，使得偏航角（$\alpha$）与滚转角（$\gamma$）的旋转效果完全耦合，无法独立区分。这正是旋转矩阵退化的几何根源，也是万向节死锁的物理表现。

#### 4.3.1 基于坐标变换的解析证明（$\beta = 90^\circ$）
设初始随体坐标系 $\{E_0\}$ 与固定坐标系 $\{A\}$ 重合，其基矢量在固定系中的表示为：  
$$
\boldsymbol{x}_{E0} = \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \quad
\boldsymbol{y}_{E0} = \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}, \quad
\boldsymbol{z}_{E0} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
$$

采用 Z-Y-X 内旋顺序（即：先绕当前随体 Z 轴转 $\alpha$，再绕新 Y 轴转 $\beta$，最后绕新 X 轴转 $\gamma$），总旋转矩阵为：  
$$
 R = R_z(\alpha) \cdot R_y(\beta) \cdot R_x(\gamma) 
$$

我们逐步追踪随体坐标轴在固定系 $\{A\}$ 中的方向变化。

**步骤 1：绕 **$\{E_0\}$** 的 Z 轴旋转 **$\alpha$**（得到 **$\{E_1\}$**）**  
旋转后，随体轴在固定系中的表示为：  
$$
\begin{aligned}
\boldsymbol{x}_{E1} &= R_z(\alpha) \cdot \boldsymbol{x}_{E0} = \begin{bmatrix} \cos\alpha \\ \sin\alpha \\ 0 \end{bmatrix}, \\
\boldsymbol{y}_{E1} &= R_z(\alpha) \cdot \boldsymbol{y}_{E0} = \begin{bmatrix} -\sin\alpha \\ \cos\alpha \\ 0 \end{bmatrix}, \\
\boldsymbol{z}_{E1} &= R_z(\alpha) \cdot \boldsymbol{z}_{E0} = \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}
\end{aligned}
$$

**步骤 2：绕 **$\{E_1\}$** 的 Y 轴旋转 **$\beta = 90^\circ$**（得到 **$\{E_2\}$**）**  
应用绕 Y 轴旋转 $90^\circ$ 的矩阵 $R_y(90^\circ) = \begin{bmatrix} 0 & 0 & 1 \\ 0 & 1 & 0 \\ -1 & 0 & 0 \end{bmatrix}$，此步骤的复合旋转矩阵为 $R_{(2)} = R_z(\alpha) \cdot R_y(90^\circ)$。各随体轴在固定系中的表示变为：  
$$
\begin{aligned}
\boldsymbol{x}_{E2} &= R_z(\alpha) \cdot R_y(90^\circ) \cdot \boldsymbol{x}_{E0} = R_z(\alpha) \cdot \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}, \\
\boldsymbol{y}_{E2} &= R_z(\alpha) \cdot R_y(90^\circ) \cdot \boldsymbol{y}_{E0} = R_z(\alpha) \cdot \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} = \begin{bmatrix} -\sin\alpha \\ \cos\alpha \\ 0 \end{bmatrix}, \\
\boldsymbol{z}_{E2} &= R_z(\alpha) \cdot R_y(90^\circ) \cdot \boldsymbol{z}_{E0} = R_z(\alpha) \cdot \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} = \begin{bmatrix} \cos\alpha \\ \sin\alpha \\ 0 \end{bmatrix}
\end{aligned}
$$

此时，随体 X 轴已指向固定系的负 Z 方向，且不再依赖于 $\alpha$；而随体 Z 轴位于固定系的 XY 平面内，方向由 $\alpha$ 决定。

**步骤 3：绕 **$\{E_2\}$** 的 X 轴旋转 **$\gamma$**（得到最终坐标系 **$\{E_3\}$**）**  
此步骤的总旋转矩阵为 $R = R_z(\alpha) \cdot R_y(90^\circ) \cdot R_x(\gamma)$。计算最终各随体轴在固定系中的方向：

+ 随体 X 轴：  
$$
\begin{aligned}
\boldsymbol{x}_{E3} &= R \cdot \boldsymbol{x}_{E0} = R_z(\alpha) \cdot R_y(90^\circ) \cdot R_x(\gamma) \cdot \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} \\
&= R_z(\alpha) \cdot R_y(90^\circ) \cdot \begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}
\end{aligned}
$$
→ 随体 X 轴方向固定，与 $\alpha$、$\gamma$ 均无关。
+ 随体 Z 轴：  
$$
\begin{aligned}
\boldsymbol{z}_{E3} &= R \cdot \boldsymbol{z}_{E0} = R_z(\alpha) \cdot R_y(90^\circ) \cdot R_x(\gamma) \cdot \begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix} \\
&= \begin{bmatrix} \cos(\alpha - \gamma) \\ \sin(\alpha - \gamma) \\ 0 \end{bmatrix}
\end{aligned}
$$
+ 随体 Y 轴：  
$$
\begin{aligned}
\boldsymbol{y}_{E3} &= R \cdot \boldsymbol{y}_{E0} = R_z(\alpha) \cdot R_y(90^\circ) \cdot R_x(\gamma) \cdot \begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix} \\
&= \begin{bmatrix} -\sin(\alpha - \gamma) \\ \cos(\alpha - \gamma) \\ 0 \end{bmatrix}
\end{aligned}
$$

#### 4.3.2 几何结论
1. 随体 X 轴 $\boldsymbol{x}_{E3} = \begin{bmatrix} 0 \\ 0 \\ -1 \end{bmatrix}$ 在空间中完全固定，后续绕该轴的旋转（即滚转 $\gamma$）无法改变其方向；
2. 随体 Z 轴与 Y 轴均位于固定系的 XY 平面内，且仅由组合量 $(\alpha - \gamma)$ 决定，与 $\alpha$、$\gamma$ 单独取值无关；
3. 偏航角 $\alpha$ 与滚转角 $\gamma$ 的旋转效果完全耦合：任意改变 $\alpha$ 和 $\gamma$，只要保持 $\alpha - \gamma$ 不变，最终姿态始终不变；
4. 几何本质：当 $\beta = 90^\circ$ 时，第一次旋转的轴（初始随体 Z 轴）与第三次旋转的轴（最终随体 X 轴）在空间中重合（均垂直于中间随体 Y 轴），导致两个独立旋转自由度退化为一个；
5. 这正是旋转矩阵秩亏、雅可比矩阵奇异的几何表现，也是万向节死锁的物理根源。

万向节死锁并非 “轴矢量消失”，而是两个旋转轴在空间中对齐，导致参数冗余与自由度丢失。在 $\beta = \pm 90°$ 时，Z-Y-X 欧拉角无法唯一描述三维姿态，必须切换参数化方式（如使用四元数或不同旋转顺序）以避免奇异性。

### 4.4 工程中的死锁规避策略
万向节死锁是欧拉角 “轴序旋转” 数学特性的必然结果，无法从根本上消除，但可通过以下工程手段适配机器人应用场景：

#### 4.4.1 选择适配场景的旋转轴序
根据机器人的工作姿态范围，选择 “死锁角度不在工作区内” 的轴序。例如：

+ 移动机器人（AGV）常用 X-Y-Z 内旋顺序，其死锁角度为 Y 轴旋转 ±90°，但移动机器人的俯仰角（Y 轴旋转）通常限制在$[-30^\circ, 30^\circ]$，可规避死锁；
+ 某些机械臂采用 Z-Y-Z 顺序（经典欧拉角，<font style="color:rgb(44, 44, 54);">指</font>**首尾轴相同**<font style="color:rgb(44, 44, 54);">的旋转序列如 Z-X-Z、Y-X-Y</font>），其死锁发生在第二个 Y 轴旋转 ±90°，若任务中俯仰角变化小，可有效降低触发概率。

#### 4.4.2 约束姿态工作空间
在运动规划算法中添加 “死锁区域避障” 逻辑：当姿态计算结果接近 β=±90° 时，自动调整目标姿态（如将 β 偏移 5°），或切换旋转轴序重新计算，确保刚体始终在 “非退化区域” 内运动。

#### 4.4.3 采用无死锁的姿态表示
在高精度、全姿态覆盖场景（如无人机悬停、航天机器人），用四元数或旋转向量替代欧拉角：

+ 四元数通过 4 个参数描述三维旋转，避免轴序依赖，从数学上消除死锁；
+ 旋转向量（轴角表示）用 “旋转轴方向 + 旋转角度” 的 3 个参数（旋转轴是单位向量，有 2 个自由度，如俯仰和偏航角，加上 1 个旋转角，共 3 个参数）描述，同样无死锁问题，且更直观。

## 5 欧拉角在机器人学中的典型应用（内旋为主）
欧拉角的 “单轴旋转直观性” 使其在机器人控制中仍有不可替代的优势，尤其内旋逻辑因贴合刚体运动特性，成为以下场景的主流选择：

### 5.1 工业机械臂的关节与末端姿态控制
6 轴串联机械臂的关节多为 “绕固定轴线的旋转关节”，每个关节的运动本质是 “绕关节随体轴的内旋”—— 这与欧拉角内旋 “分解为单轴随体旋转” 的逻辑高度契合。

+ 关节角映射：机械臂逆运动学求解中，通常将末端目标姿态（如 Z-Y-X 内旋欧拉角）转换为各关节的旋转角度（如基座关节绕 Z 轴转 α，小臂关节绕 Y 轴转 β），通过 “单关节位置闭环控制” 实现姿态跟踪；
+ 工艺适配示例：精密装配机器人拧紧螺钉时，需将末端工具姿态定义为 “Z 轴沿螺钉轴线（内旋 Z 轴），X 轴沿进给方向（内旋 X 轴）”，此时用欧拉角（α=0, β=0, γ=0）描述目标姿态，可直接映射为关节的单轴旋转指令，控制精度可达 ±0.01°。

### 5.2 移动机器人的位姿描述与导航控制
移动机器人（如 AGV、自动驾驶小车）的 “位姿（Pose）” 由 “位置（x, y）” 和 “姿态（欧拉角）” 组成，其中姿态多采用 X-Y-Z 内旋顺序描述，适配地面运动场景：

+ 偏航角（Yaw）：绕随体 Z 轴（垂直地面）的内旋角度，对应机器人 “航向角”—— 导航中通过 PID 控制 Yaw 角，使机器人沿预定路径行驶（如跟踪激光导航线时，Yaw 角偏差需控制在 ±1° 内）；
+ 俯仰角（Pitch）：绕随体 Y 轴（水平向左）的内旋角度，反映机器人行驶坡度 —— 通过 IMU 检测 Pitch 角，补偿激光雷达或视觉传感器的测量偏差（如坡道上 Pitch 角 = 5° 时，需修正传感器距离测量值）；
+ 滚转角（Roll）：绕随体 X 轴（前进方向）的内旋角度，用于侧翻风险检测 —— 当 Roll 角绝对值超过 15° 时，触发底盘平衡机构或紧急停车，避免机器人侧翻。

### 5.3 机器人传感器标定与姿态融合
机器人常用的 IMU（惯性测量单元）、视觉传感器等，其姿态输出需与机器人本体坐标系对齐，欧拉角（尤其是内旋）是关键的 “中间转换载体”：

+ 传感器标定：IMU 输出的角速度通常基于自身坐标系，需通过 Z-Y-X 内旋欧拉角将其转换为机器人本体坐标系（如 IMU 安装偏角 α=10°，需将 IMU 的 X 轴角速度旋转 10° 后映射到机器人 X 轴，需通过一个由安装偏角（如 α=10°）构成的旋转矩阵，将测量到的 IMU 坐标系下的角速度矢量转换到机器人本体坐标系下。）；
+ 多传感器融合：SLAM（同步定位与地图构建）中，轮速计输出的位置与 IMU 输出的姿态需融合 —— 欧拉角可将 IMU 的内旋姿态（如 Yaw 角）与轮速计的航向偏差关联，通过卡尔曼滤波修正机器人位姿漂移。

## 6 欧拉角与其他姿态表示的对比
下表对比机器人学中常用的四种姿态表示方法，突出欧拉角（内旋）的优劣势：

| 姿态表示方法 | 核心逻辑 | 参数数量 | 有无死锁 | 计算效率（内旋复合） | 机器人学适配场景 |
| --- | --- | --- | --- | --- | --- |
| 欧拉角（内旋） | 随体轴连续单轴旋转 | 3 | 有 | 中等（矩阵乘法） | 机械臂关节控制、移动机器人导航 |
| 欧拉角（外旋） | 固定轴连续单轴旋转 | 3 | 有 | 中等（矩阵乘法） | 地面固定设备姿态检测 |
| 四元数 | 4 维复数描述旋转 | 4 | 无 | 高（四元数乘法） | 无人机姿态控制、SLAM 姿态更新 |
| 旋转向量 | 轴方向 + 角度的 3 维向量 | 3 | 无 | 低（需转矩阵复合） | 姿态误差表示、机器人标定 |

可见，欧拉角（内旋）的核心优势是 “直观性与参数少”，适合需人工干预或单轴控制的场景；而四元数因无死锁、计算高效，更适配全姿态覆盖的高精度控制场景。

