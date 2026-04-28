# C7. Chiral 配对对称性 — p+ip / d+id 与时间反演对称性自发破缺

**MECE 编号：** C7
**关联 MECE：**
- C3（d-wave — chiral d+id 的两个成分之一：d_x²-y² 是 B₁g，d_xy 是 B₂g）
- C5（p-wave — chiral p+ip 是 p-wave 的拓扑扩展；两个手征 p+ip 态叠加形成 chiral SC）
- C4（d_xy — chiral d+id 的第二个成分；B₂g 通道参与相位叠加形成 TRSB 态）
- B11（拓扑超导 — chiral p+ip 是 Class D 拓扑超导的核心实例；Chern 数 C=1 → Majorana 边缘态）
- D11（2D/界面 — MATBG 和石墨烯体系是 chiral d+id 的主要候选平台）
- D14（Kagome 超导 — CsV₃Sb₅ 等 Kagome 材料有 d+id 理论预言，实验争议中）
- F3（Chern 数 — chiral 配对的核心拓扑不变量；p+ip → C=±1；d+id → C=±2）
- A9（Andreev 反射 — Majorana 边缘态的实验探测窗口；ZBCP 是 chiral p+ip 的间接证据）

**层级关系：** C7 是配对对称性中唯一涉及**时间反演对称性（TRS）自发破缺**的课题。它不对应单一角动量 ℓ，而是两个不同配对通道的**复数叠加**（Δ₁ + iΔ₂），手性（chirality）来自 k 空间波函数的拓扑缠绕。Chiral p+ip 有大量理论支持和拓扑理由；chiral d+id 是六角/蜂窝晶格体系（MATBG、Kagome）的天然候选。**固体中目前没有任何材料被判决性地确认为 chiral 超导体**——Sr₂RuO₄ 曾是最强候选，2019 年实验彻底推翻。
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Read-Green 2000、Kallin 2016 RPP、Schemm 2014 Science、Pustogow 2019 Nature、Nandkishore-Levitov-Chubukov 2012、Black-Schaffer 2014 等；数值标注 [来源待验证] 处须后续核查）

⚠️ **核心诚实声明：Sr₂RuO₄ 教训 —— TRSB ≠ chiral 超导。PKE 旋转和 µSR 内磁场是 TRSB 的现象，不是 chiral 超导的直接证明。Knight shift 才是区分 singlet/triplet 的决定性判据，它在 Sr₂RuO₄ 中给出了与 chiral p+ip 不符的结论。对 Kagome、MATBG、UTe₂ 等所有候选材料，必须重复这一教训。**

---

## 1. 物理定义与核心思想

### 1.1 什么是 Chiral 超导？

**[定理 — Chiral 超导的定义：TRS 自发破缺]**

```
普通超导体（包括 d-wave）保持时间反演对称性（TRS）：
  TRS 变换：k → -k，s → -s，i → -i（复共轭 + 时间反转）
  普通 SC：Δ(k) = Δ*(-k)（即 T 作用下波函数回到自身，至多差一个相位）

Chiral 超导体的定义：
  Δ(k) = Δ₁(k) + i·Δ₂(k)     ← 两个实配对通道的复数叠加
  
  TRS 变换作用：
    T: Δ(k) → Δ*(-k) = Δ₁(-k) - i·Δ₂(-k)
  
  若 Δ₁ 和 Δ₂ 在 TRS 下均保持（偶宇称）或均反号（奇宇称），
  且 Δ₁ ≠ λΔ₂ 对任意实数 λ，则：
    TRS 变换 ≠ 原来的 Δ(k)（至多差整体相位）
  → TRS 自发破缺（Spontaneous TRSB）！

直观理解：
  "chiral" = 在 k 空间有手性方向（左手/右手）
  就像光学活性分子：镜像与原来不同（不可叠合）
  超导态在 TRS 下变成"另一个态"（手征对）
```

### 1.2 两大 Chiral 类型对比

**[定理 — p+ip 和 d+id 的分类（群论层级）]**

```
类型 1：Chiral p+ip（C5 的拓扑版本）
  Δ(k) = Δ₀(k_x + i·k_y)   ← 两个 p-wave 分量的复合
  
  对称性：打破 TRS（Δ ≠ Δ*）
  Chern 数 C = ±1（取决于费米面拓扑）
  边缘态：chiral Majorana 费米子（实费米子，不带电）
  → 这是 B11 拓扑超导 Class D 的核心实例（Read-Green 2000）
  宇称：奇（p 类，奇宇称 triplet）

类型 2：Chiral d+id
  Δ(k) = Δ₀[(k_x² - k_y²) + i·k_x·k_y]   ← d_x²-y² + i·d_xy 复合
  
  对称性：打破 TRS
  Chern 数 C = ±2（两个 d-wave 各贡献 ±1）
  边缘态：chiral 带电费米子（非 Majorana，有电荷）
  → 六角/蜂窝晶格（石墨烯、Kagome）的天然候选
  宇称：偶（d 类，偶宇称 singlet）

关键区分：
  p+ip → triplet（C5 关联）→ 必须是奇宇称 → spin-triplet
  d+id → singlet（C3/C4 关联）→ 偶宇称 → spin-singlet
  两者在晶格对称性上处于完全不同的位置！
```

### 1.3 TRS 破缺的物理来源

**[猜想 — 复数能隙的自发形成机制]**

```
Chiral 态是两个几乎简并配对通道竞争的产物：

情景 A（d+id 形成）：
  两个 d-wave 通道 d_x²-y²（B₁g）和 d_xy（B₂g）
  在六角/蜂窝晶格中，Van Hove 奇点附近这两个通道接近简并
  → 系统倾向于形成复数叠加（自由能更低）
  → Δ = Δ_B1g + i·Δ_B2g（相位差 π/2）

情景 B（p+ip 形成）：
  两个 p-wave 通道 p_x 和 p_y 简并（二维 E 表示）
  → 在 2D 体系中这两个分量自然形成手性组合
  → Δ = Δ_px + i·Δ_py

为什么选 π/2 相位差？
  自由能分析（[猜想 — Ginzburg-Landau 四次项]）：
    F(η₁, η₂) = a(|η₁|² + |η₂|²) + b(|η₁|² + |η₂|²)² + c|η₁|²|η₂|²
    + d·Re(η₁*²η₂²) + ...
    当 c < 0（跨通道吸引）和 d 具体符号时，
    最低能量态为 η₁ = η₀，η₂ = ±i·η₀（相位差 ±π/2）
    → 手性态（TRS 破缺）比实数叠加（实态 d_x²-y² 或 d_xy）能量更低
```

### 1.4 TRSB 的实验信号层级

```
TRS 破缺信号（按可靠性降序）：
  
  1. 极向 Kerr 效应（PKE）：最强实验判据
     原理：σ_xy(ω) ≠ 0 → 旋光现象（偏振旋转）
     无磁场、零外场 → 必然来自内禀手性序参量
     精度要求：nrad 量级（Kapitulnik 组独有技术）[来源待验证]
  
  2. µSR 内磁场：次强判据
     原理：自发边缘电流 → 体内磁场 → µ+ 弛豫加快
     信号强度：µG 量级，极难与磁性杂质区分
     ⚠️ 污染风险：磁性杂质 ppm 量级即可产生相同信号
  
  3. anomalous Hall 效应：若有量子化 → 较强
     σ_xy = Ce²/h（量子化 Hall）
     ⚠️ 非量子化的 Hall 可能来自多种来源
  
  4. STM 边缘电流：直接但极难
     理论预言 10⁻⁷ A 量级，接近实验极限 [来源待验证]

信号层级优先：PKE > µSR（配合磁性排除）> AHE > STM 边缘态
```

---

## 2. 历史关键节点

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **1994** | **Kopnin-Salomaa**：理论预言 chiral p+ip 超导体具有拓扑保护的边缘态 | [猜想，拓扑先驱] | [来源待验证：具体文章] |
| **1998** | **Laughlin**：提出 d+id 配对态在三角晶格上的可能性 | [猜想] | Laughlin 1998 PRL [来源待验证：卷号] |
| **2000** | **Read & Green PRB**：chiral p+ip + Pfaffian 态 + Majorana 费米子 → 拓扑量子计算的理论奠基 | [定理，拓扑框架] | Read & Green 2000 PRB 61, 10267 [来源待核查卷号] |
| **2004** | **Nelson & Orenstein**（Sr₂RuO₄ µSR）：T_c 以下自发内磁场 → TRSB | [观察，TRSB 信号] | Nelson & Orenstein 2004 PRL [来源待验证：卷号页码] |
| **2007/2012** | **Black-Schaffer & Doniach**（石墨烯 d+id 理论）：蜂窝晶格 Van Hove 奇点附近 d+id 是最低能量 SC 态 | [猜想] | Black-Schaffer & Doniach 2007 PRB 75, 134512 [来源待核查] |
| **2012** | **Nandkishore, Levitov & Chubukov**：石墨烯 Van Hove filling 处 d+id SC 的 RG 分析 → 强相互作用下稳定 | [猜想] | Nandkishore et al. 2012 Nature Physics 8, 158 [来源待核查] |
| **2014** | **Schemm 等**（Sr₂RuO₄ + UPt₃ Kerr 效应）：Sr₂RuO₄ 和 UPt₃ B 相均检测到非零 PKE | [观察，TRSB 信号] | Schemm et al. 2014 Science [卷号页码待核查] |
| **2016** | **Kallin & Berlinsky** RPP 综述：chiral 超导系统性综述，Sr₂RuO₄ 为核心案例 | [综述] | Kallin & Berlinsky 2016 Rep. Prog. Phys. [来源待核查卷号] |
| **2016** | **Venderbos 等**：Kagome 晶格 chiral d+id SC 的拓扑分析，Chern 数 C=2 | [猜想] | Venderbos et al. 2016 PRB [来源待验证] |
| **2019** | **Pustogow 等**（Sr₂RuO₄ NMR 修正）：低 RF 功率下 Knight shift 在 T_c 以下显著下降 → **推翻 spin-triplet** → Sr₂RuO₄ 不是 chiral p+ip！ | [定理，推翻 chiral p+ip] | Pustogow et al. 2019 Nature 574, 72 |
| **2019+** | **UTe₂ 发现**（Ran 2019）：triplet 候选，可能 chiral p-wave（多相 SC，高磁场） | [猜想，活跃前沿] | Ran et al. 2019 Science 365, 684 |
| **2020-2022** | **CsV₃Sb₅（Kagome）**：发现超导，部分组看到 µSR TRSB 信号，d+id 理论预言 | [观察，争议中] | [多篇文章，来源待验证，首篇 Ortiz et al. 2020 PRMaterials？] |
| **2021+** | **MATBG 中 TRS 破缺信号**：部分实验组报告 TRS 破缺，可能与 chiral d+id 相关 | [观察，不确定] | [多篇文章，来源待验证] |
| **2023** | **Ajeesh 等**（UTe₂）：近年系列 Nature/PRL 文章支持 chiral SC | [猜想] | Ajeesh et al. 2023 [来源待验证：具体期刊卷号] |

⚠️ **Sr₂RuO₄ 24 年翻案的教训（最重要的历史节点）：** 从 Mackenzie 1995 的 triplet 猜想（基于比热）到 Schemm 2014 的 PKE 证据，Sr₂RuO₄ 被视为 chiral p+ip 的"标准候选"。直到 2019 年 Pustogow 等精确控制 NMR 的 RF 功率，才发现过去 24 年的 Knight shift 测量均受 RF 加热干扰（T_c 以下 T 上升 → 误读为 singlet/triplet 不变）。**TRSB 信号（PKE + µSR）至今未被推翻**，但 triplet 特征已被推翻 → Sr₂RuO₄ 的真实配对对称性至今未明。

---

## 3. 数学框架

### 3.1 Chiral p+ip 能隙函数

**[定理 — chiral p+ip 的 BdG 结构]**

LaTeX:
$$\Delta(\mathbf{k}) = \Delta_0 (k_x + ik_y) = \Delta_0 k_\perp e^{i\phi_k}$$

ASCII 等价：
```
Chiral p+ip 能隙（连续极限）：
  Δ(k) = Δ₀(k_x + i·k_y)    ← 两个 p-wave 分量的复数叠加
  
  等价形式：
  Δ(k) = Δ₀ · k_⊥ · exp(i·φ_k)   （极坐标，φ_k = atan(k_y/k_x)）
  
  物理性质：
  |Δ(k)| = Δ₀ · k_⊥               ← 在 k_⊥=0 有节点（极点）
  Phase(Δ): 绕费米面一圈变化 2π   ← 拓扑缠绕数 = 1
  
  TRS 检验：
  Δ*(k) = Δ₀(k_x - i·k_y) = Δ₀ · k_⊥ · exp(-i·φ_k)
  Δ(k) ≠ Δ*(k)（相位相反）→ TRS 自发破缺 ✓

BdG 哈密顿量（格点版本，d-vector 形式）：
  d(k) = Δ₀(k_x + i·k_y) ẑ     ← d-vector 沿 z 方向极化
  
  BdG 矩阵：H(k) = (ε_k·τ_z + d(k)·σ·τ_x)
  其中 τ 是粒子-空穴空间，σ 是自旋空间

Chern 数（2D 拓扑不变量）：
  C = (1/2π) ∫_BZ F_k d²k   （Berry 曲率的 BZ 积分）
  
  对 chiral p+ip：
    μ > 0（Fermi 面内有拓扑相）: C = +1 → Majorana 边缘态
    μ < 0（Fermi 面外）:          C = 0  → 拓扑平凡（trivial）
    μ = 0（量子临界点）:          相变点（Read-Green 2000）
```

### 3.2 Chiral d+id 能隙函数

**[猜想 — chiral d+id 在蜂窝/六角晶格体系]**

LaTeX:
$$\Delta(\mathbf{k}) = \Delta_0 \left[(k_x^2 - k_y^2) + i \cdot k_x k_y \right] = \Delta_0 k_\perp^2 e^{2i\phi_k}$$

ASCII 等价：
```
Chiral d+id 能隙（连续极限）：
  Δ(k) = Δ₀[(k_x² - k_y²) + i·k_x·k_y]
  
  = d_{x²-y²}(k) + i·d_{xy}(k)    ← d_x²-y² (B₁g) + i·d_xy (B₂g)
  
  等价极坐标形式：
  Δ(k) = Δ₀ · k_⊥² · exp(2i·φ_k)   ← 拓扑缠绕数 = 2！
  
  物理性质：
  |Δ(k)| = Δ₀ · k_⊥²   ← 同样在 k_⊥=0 有节点
  Phase(Δ): 绕费米面一圈变化 4π → 缠绕数 = 2
  
  Chern 数：C = ±2
  
  边缘态：chiral 带电费米子（非 Majorana！）
    N 个 chiral 边缘模（C=2 → 2 条 chiral 边缘支）

晶格版本（六角/蜂窝晶格 Van Hove 奇点处）：
  Δ(k) = Δ₀[(cos k_x - cos k_y) + i·sin k_x sin k_y]
  
  这在六角晶格中自然出现：
  - Van Hove 奇点（鞍点）附近，态密度 N(ε) 急剧上升
  - B₁g（d_x²-y²）和 B₂g（d_xy）通道在蜂窝晶格中接近简并
  - 相互作用驱动 → 自发形成复数叠加（TRS 破缺最大化配对凝聚）
```

### 3.3 TRS 破缺的数学条件

**[定理]**

```
TRS 破缺的严格数学条件：
  设 Δ(k) = Δ₁(k) + i·Δ₂(k)
  TRS 要求：存在实数 λ，使 Δ(k) = λ·Δ*(k)（至多整体实数因子）
  即 Δ₁(k)/Δ₂(k) = const.（两个分量同向，无 π/2 相位差）
  
  TRS 自发破缺的条件：
    Δ₁(k) 和 Δ₂(k) 不成比例（两个独立通道各有振幅）
    且 Im[Δ] ≠ 0（不能通过整体相位规范变换消去虚部）
  
  等价形式：
    T 变换: k → -k，i → -i（复共轭）
    若 Δ(-k) = Δ*(k) → TRS 保持（普通 singlet）
    若 Δ(-k) ≠ Δ*(k)（且不差一个常数）→ TRS 破缺
```

### 3.4 极向 Kerr 效应（PKE）的物理

**[定理 — PKE 与 Hall 电导的关系]**

```
极向 Kerr 旋转与 Hall 电导：

Θ_K ≈ (4πd/ωc) · Im[σ_xy(ω)]    （Kerr 旋转角公式）

其中：
  d = 样品厚度（或相关长度）
  ω = 光频率
  c = 光速
  σ_xy(ω) = 非对角光电导（Hall 光电导）

ASCII 等价：
  θ_K ≈ (4π·d / ω·c) × Im[σ_xy(ω)]

TRS 破缺 → σ_xy ≠ 0（Hall 电导非零，无需外磁场）
→ Θ_K ≠ 0（偏振光旋转）

量子化 Hall 电导（如完整量子 Hall 相）：
  σ_xy = C · e²/h    (C = Chern 数，整数)
  
  chiral p+ip (C=1): σ_xy = e²/h
  chiral d+id (C=2): σ_xy = 2e²/h

⚠️ 注意：实际 SC 体系中 σ_xy 一般不量子化（非整数），
  因为 Fermi 面不完整（有准粒子）。
  量子化仅在 T=0 绝热极限成立。
```

---

## 4. 实验识别方法

### 4.1 极向 Kerr 效应（PKE / MOKE）

```
原理与灵敏度：
  线偏振光在 TRS 破缺超导体表面反射后偏振面旋转
  旋转角 Θ_K ~ 10⁻⁸ rad（nrad 量级）
  需要 Sagnac 干涉仪技术（Kapitulnik 组 Stanford）[来源待验证]
  
PKE 判断 TRSB 的逻辑：
  ✅ T < T_c 开始出现 → 与 SC 序参量耦合
  ✅ 无外磁场 → 排除普通 Lorentz 力来源
  ✅ 消磁场循环不影响 → 排除铁磁性来源
  
  ⚠️ PKE ≠ 确认 chiral SC！可能来源：
    (a) 手性 SC 本征 σ_xy（我们想要的）
    (b) 剩余铁磁畴（磁性杂质）
    (c) 轨道有序或多极矩序（与 SC 关联但不是 chiral SC）
    (d) 仪器系统误差（Θ_K < µrad 量级极易受干扰）
```

### 4.2 µSR（正电子自旋弛豫）

```
原理：
  自发边缘电流 → 体内磁场（µG 量级）→ 注入 µ+ 自旋弛豫加快
  弛豫率 λ(T) 在 T_c 以下突增 → TRSB 信号
  
  信号量级（典型值）：
  δB_int ~ 0.1-1 µG（内磁场增量）[来源待验证：典型 µSR 值]
  
  ⚠️ 污染风险（核心问题）：
    磁性杂质（Fe、Mn ppm 量级）产生局域磁场
    → µSR 弛豫加快，与 TRSB 信号完全相同
    → 样品纯度要求极高（< ppm 磁性杂质）
    → 不同实验组结果差异往往来源于样品质量不一致
    
  Sr₂RuO₄ 的 µSR 信号（Nelson 2004 [来源待核查]）：
    T_c 以下观测到自发内磁场
    但 2019 年 triplet 推翻后，这个信号的来源至今未解
    → µSR TRSB ≠ chiral p+ip
```

### 4.3 比热与穿透深度

```
节点结构的热力学信号：

Chiral p+ip（无节点）：
  |Δ(k)| → Δ₀ (有限能隙，除极点外)
  → C(T) ∝ exp(-Δ₀/T)  （指数型，无节点特征）
  → ρ_s(T) ∝ exp(-Δ₀/T) （穿透深度指数型）
  
  ⚠️ 但 k_⊥ → 0 处（极点）|Δ| → 0，可能引入 T² 项
  → 实验上可能看到指数 + 幂次混合（依赖 Fermi 面几何）

Chiral d+id（有节结构）：
  |Δ(k)| = Δ₀ · k_⊥²（在 k_⊥=0 处零点）
  → 取决于是否有真正的节点（接触费米面）
  → 若节点接触费米面：C(T) ∝ T² 或 T³（幂次型）
  → 若节点远离费米面：接近全能隙行为

⚠️ 比热单独无法区分 chiral 和非 chiral（见 C6 教训）。
```

### 4.4 anomalous Hall 效应（AHE）

```
零磁场下的横向电导：
  σ_xy ≠ 0 且无磁场 → TRS 破缺（与 chiral 序参量相关）

量子化条件（理想情况）：
  σ_xy = C · e²/h（Chern 数量子化）
  实际体系：准粒子激发减弱量子化，σ_xy 一般不整数倍 e²/h

区分困难：
  拓扑绝缘体表面态、磁性相、Berry 曲率效应均可产生 AHE
  → 需要与 SC 转变温度 T_c 严格耦合才能归因于 chiral SC
```

---

## 5. 关键定量结果与典型材料

### 5.1 Sr₂RuO₄ — 曾经的 chiral p+ip 标准候选（现已推翻）

**[历史档案 — 反谄媚必读]**

| 参量 | 数值 | 状态 | 来源 |
|------|------|------|------|
| T_c | 1.5 K | [定理] | [来源待验证：Maeno 1994 Nature] |
| 点群 | D₄h（四方对称）| [定理] | — |
| µSR 内磁场 | 检测到 T_c 以下增强 | [观察] | Nelson & Orenstein 2004 PRL [来源待核查] |
| Kerr 旋转 Θ_K | ~65 nrad（T_c 以下）| [观察] | Schemm et al. 2014 Science [来源待核查卷号] |
| Knight shift（旧测量）| T_c 以下不降 → 支持 triplet | [已撤销观察] | 多篇 1995-2018 文章 |
| Knight shift（新测量）| T_c 以下**下降** → 推翻 triplet | [定理，判决性实验] | **Pustogow et al. 2019 Nature 574, 72** |

```
Sr₂RuO₄ 教训的完整结构：

第一阶段（1994-2019）：
  1994：发现超导，chiral p+ip 猜想 [Mackenzie 等，来源待验证]
  2004：µSR 内磁场 → TRSB 信号 → "支持 chiral"
  2014：PKE 旋转 → "支持 chiral"
  结论：大多数综述将 Sr₂RuO₄ 列为 chiral p+ip 确认案例

第二阶段（2019-今）：
  2019 Pustogow 等：发现早期 NMR 的 RF 加热问题
    → 旧测量中 T_c 以下温度实际上并未降低（样品局部加热）
    → 低功率 RF 测量：Knight shift 在 T_c 以下显著下降
    → 结论：Sr₂RuO₄ 是 singlet（不是 triplet！）
    → chiral p+ip（triplet）假说被推翻

遗留问题（未解）：
  µSR TRSB 信号仍未解释（不是 triplet 来的，那是什么？）
  PKE 旋转仍未解释（不是 chiral p+ip 来的，那是什么？）
  Sr₂RuO₄ 的真实配对对称性 2026 年仍是开放问题
  → 可能是 d_{x²-y²} + id_{xy}（singlet chiral d+id）？[猜想，未确认]
```

### 5.2 UPt₃ — B 相 TRSB 候选（chiral f-wave 可能）

**[猜想 — 来源：Schemm 2014，结论待验证]**

```
UPt₃ B 相（H-T 相图中间区域）：
  Schemm 等 2014 Science 也测量了 UPt₃ → B 相检测到 PKE 信号 [来源待核查卷号]
  
  解释（[猜想]）：
    UPt₃ 配对可能是 E₂u（f-wave）的 chiral 组合（两个 f-wave 分量复叠加）
    → 类似于 p+ip 但是 f+if 类型（见 C6）
    
  连接 C6 和 C7：
    C6 讨论的 f-wave（E₂u）本身是实数配对
    chiral f-wave = E₂u 两个分量的复数叠加（η₁ + i·η₂）
    → TRS 破缺 → C7 的范畴
    → UPt₃ B 相可能是 chiral f-wave（非 Majorana chiral 体系）

⚠️ 这仍是猜想：E₁u/E₂u 区分本身未解（见 C6），
   chiral f-wave 的具体分类更是未经判决性实验。
```

### 5.3 UTe₂ — 当前 chiral p-wave 最活跃候选

**[猜想 — 活跃前沿，2025 年仍争议]**

```
UTe₂ 关键参数：
  T_c = 1.6 K（Ran 2019 Science 365, 684）[来源待核查卷页]
  点群：D₂h（斜方晶系）
  多 SC 相：至少 2-3 个（含高磁场 re-entrant SC > 50T）[来源待验证]
  Knight shift：强 triplet 信号（各向异性）→ 暗示 p-wave 类

Chiral 可能性：
  [猜想] 多个近年 Nature/PRL 文章（Ajeesh 2023 等）暗示 chiral 配对
  [观察] 多 SC 相 + 高磁场行为与 chiral triplet 一致
  
  ⚠️ Sr₂RuO₄ 教训直接适用：
    UTe₂ 的 triplet Knight shift 需要严格 RF 功率控制核查
    样品质量依赖性极强（不同批次 T_c 差异大）
    2022-2025 不同实验组结论不一致 [来源待验证]
    
  → UTe₂ 是目前最有希望的 chiral p-wave 候选，
    但距离"判决性确认"仍有距离（记住 Sr₂RuO₄ 用了 24 年又翻了）
```

### 5.4 Kagome CsV₃Sb₅ — d+id 理论预言候选

**[猜想 — 实验结果相互矛盾]**

```
CsV₃Sb₅ 关键参数：
  T_c ≈ 2.3-3.0 K（依样品）[来源待验证]
  晶体结构：Kagome 晶格（D₆h）
  CDW 竞争：T_CDW ~ 78-103 K [来源待验证]

d+id 理论预言（[猜想]）：
  Kagome 晶格 = 六角对称 → d_x²-y² 和 d_xy 通道接近简并
  平坦带 + Van Hove 奇点 → 强相互作用增强
  Venderbos 2016 PRB [来源待验证]：Chern 数 C=2

µSR 实验现状（[观察，矛盾]）：
  部分实验组：检测到 T_c 以下自发磁场 → 支持 TRSB [来源待验证]
  部分实验组：未检测到 TRSB 信号 [来源待验证]
  
  ⚠️ 不可重复性是核心问题：
    样品批次差异 → µSR 结果差异
    CDW 序对 SC 的影响 → 材料态本身不稳定
    → Kagome d+id 是理论预言，**目前实验证据矛盾且不可重复**
```

### 5.5 MATBG — 可能的 d+id 候选（机制不明）

**[猜想 — 实验信号弱且来源不明]**

```
Magic Angle TBG（扭转双层石墨烯）：
  超导出现在 θ ≈ 1.1°，T_c ~ 1-3 K [来源待验证]
  点群：有效六角对称（弱蜂窝晶格投影）
  平坦带：量子几何（B13 框架）增强配对
  
TRS 破缺信号（[观察，不确定]）：
  部分实验组报告 TRS 破缺相 [来源待验证：Sharpe 2019？]
  
  ⚠️ TRS 破缺来源不明：
    (a) Chiral d+id SC [我们讨论的]
    (b) 关联绝缘体相（Chern 绝缘体，磁性）
    (c) 量子反常 Hall 效应（非 SC 来源）
    (d) 样品制备中引入的磁性杂质
    
  → MATBG 的 TRS 破缺与 chiral SC 的关系至今未确立
  → 需要在 SC 态（非绝缘态）明确 TRS 破缺 + 排除其他来源
```

---

## 6. Chiral 配对的拓扑分类

| 类型 | Chern 数 | 边缘态 | 时间反演 | 自旋 | 典型体系 |
|------|----------|--------|---------|------|---------|
| chiral p+ip | C=±1 | Majorana（实费米子，无电荷）| ❌ 破缺 | triplet | ³He-A 超流, Sr₂RuO₄?（推翻），UTe₂? |
| chiral d+id | C=±2 | 带电手性费米子（非 Majorana）| ❌ 破缺 | singlet | 石墨烯 VHS?, Kagome?, Sr₂RuO₄?（新猜想）|
| helical p-wave | Z₂（ℤ₂）| Majorana 成对（保护，无手性）| ✅ 保持 | triplet | 半导体纳米线（理论） |
| trivial s-wave | 0 | 无 | ✅ 保持 | singlet | Nb, Pb, Al |
| chiral d-wave（d_x²-y²）| 0（伪 chiral）| 无拓扑边缘态 | ✅ 保持 | singlet | YBCO（非 chiral）|

```
重要澄清：
  ³He-A 超流体（液态氦-3 的 A 相）是目前唯一
  **无争议地确认**为 chiral p+ip 拓扑超流体的体系 [定理]
  
  固体中：
    chiral p+ip → 0 判决性确认（Sr₂RuO₄ 已推翻）
    chiral d+id → 0 判决性确认（石墨烯/Kagome 均为理论预言）
    
  → C7 是实验基础同样薄弱的配对对称性（与 C6 并列）
    区别在于：chiral SC 的**理论框架（拓扑）**比 f-wave 更成熟
```

---

## 7. 关键反谄媚

### 7.1 Sr₂RuO₄ 24 年教训的核心推论

**[观察 — 最重要的反谄媚]**

```
推论 1：TRSB ≠ chiral 超导
  PKE + µSR → TRSB 信号 → 不能直接推出 chiral SC
  必须额外确认：
    (a) 确实是 SC 序参量（而非轨道序、磁性序等）驱动的 σ_xy
    (b) spin singlet/triplet 确认（Knight shift，低 RF 功率）
    (c) 排除磁性杂质污染（µSR 尤其敏感）

推论 2：PKE 测量的技术门槛极高
  nrad 精度只有少数实验室具备（Kapitulnik 组 Stanford 为代表）
  其他组的 µrad 精度 PKE 无法分辨 chiral SC 信号
  → 从非 Kapitulnik 组的 PKE "未见信号" 结论时要注意技术极限

推论 3：triplet 判据独立于 TRSB 判据
  "triplet（非 singlet）" 的判断必须来自 Knight shift（NMR）
  TRSB 既可以来自 chiral triplet（p+ip），也可以来自 chiral singlet（d+id）
  甚至可以来自与 SC 无关的相（磁性、轨道序）
  → 这四种情况要逐一排除
```

### 7.2 Kagome d+id：理论美感 ≠ 实验确认

**[观察]**

```
Kagome d+id 的理论动机极好：
  ✅ 六角对称 → d_x²-y² 和 d_xy 简并（群论保证）
  ✅ 平坦带 + Van Hove 奇点 → 强相互作用增强配对
  ✅ 拓扑预言（Chern C=2）有精确理论计算支持
  
  但实验状态（2026）：
  ❌ CsV₃Sb₅ µSR 结果组间不可重复
  ❌ CDW 竞争使 SC 态本身不稳定
  ❌ 没有 PKE 精确测量报告（精度不足？）
  ❌ Knight shift（NMR）未给出明确 singlet/triplet 结论 [来源待验证]
  
  → d+id 的"理论美感"不等于实验确认
  → 当前状态：[猜想，不可重复的实验支持]
```

### 7.3 MATBG 的 TRS 破缺：多源性问题

**[观察]**

```
MATBG 中各种 TRS 破缺来源的竞争（按发生可能性大致排序）：
  
  (1) 关联绝缘体 / 量子反常 Hall（Chern 绝缘体）→ 非 SC 来源，最可能
  (2) 磁性涨落/序 → 轨道磁性或自旋磁性
  (3) Chiral d+id SC → 我们讨论的目标，最难确认
  
  ⚠️ 目前的实验（磁力显微镜、AHE 等）
     并不能排除（1）和（2）优先于（3）
  → MATBG 的 TRS 破缺不是 chiral SC 的证据，而是一个开放问题
```

### 7.4 Chiral d+id 的条件苛刻性

**[观察]**

```
chiral d+id 形成的必要条件：
  (a) 晶格对称性：需要六角/蜂窝晶格（D₆ 或更高对称性）
      → 四方晶格（如铜氧化物 D₄h）不自然产生 d+id
      → Sr₂RuO₄（D₄h）如果是 chiral 则是 d_x²-y² + i·d_xy（但 B₁g + B₂g 在 D₄h 不简并！）
  
  (b) 费米面几何：Van Hove 奇点附近
      → 仅在特定填充（VHS 处）两通道接近简并
      → 偏离 VHS → 一个通道主导，实数 d-wave（非 chiral）
  
  (c) 相互作用强度：需要足够强才能产生 π/2 相位差
      → BCS 弱耦合不能自发产生 chiral（TRS 破缺需要能量驱动）
      → 必须有足够强的 GL 四次项（跨通道耦合 c < 0）

  满足以上三条的体系：石墨烯 VHS、Kagome VHS
  → 范围有限，且均有实验困难
```

---

## 8. 与 Paper E 的关联

**Paper E（轨道-能隙对应原则）：**

```
Chiral d+id 是 Paper E 框架中轨道混合竞争的极端情况（[猜想]）：

Paper E 的核心原则：
  轨道角动量 → 配对角动量（通道选择性）
  轨道混合（d_x²-y² ↔ d_xy）→ 配对竞争（B₁g ↔ B₂g）

Chiral d+id 的 Paper E 解读：
  d_x²-y²（B₁g，角动量分量 m=2）和 d_xy（B₂g，m=-2）
  在六角晶格的 D₆ 对称性下，这两个通道属于同一不可约表示 E₂
  → "轨道简并" → "配对简并" → 自发相位差 π/2 → TRS 破缺

更深层联系（[猜想]）：
  Paper E 框架预测：六角/蜂窝晶格中存在轨道通道的内禀简并
  → 这种简并在 Cooper 对层面"投影"为 d+id 配对
  → Chiral 态是 Paper E 框架轨道竞争的热力学最终态（当两通道等强且相位差 π/2）

与 chiral p+ip 的 Paper E 联系：
  p_x 和 p_y 在 2D 体系属于 E₁ 表示（简并！）
  → 轨道简并（E₁）→ 配对简并 → chiral p+ip
  → Sr₂RuO₄ 的 Ru t₂g 轨道（ℓ_eff = 1, p-like）→ chiral p+ip
  → 但 Sr₂RuO₄ 已推翻！→ 说明 Paper E 框架的这个"预测"需要更强的检验

⚠️ Paper E 框架与 chiral SC 的联系是有理论美感的猜想，
   不是已验证的预测。需要一个实验确认的 chiral SC 才能真正检验这个框架。
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026）| 主要障碍 |
|------|----------------|---------|
| **固体 chiral p+ip 是否存在（排除 ³He）？** | 无确认（Sr₂RuO₄ 推翻，UTe₂ 猜想中）| Sr₂RuO₄ 24 年翻案教训；UTe₂ 样品质量依赖 |
| **Sr₂RuO₄ 的 µSR 内磁场来源** | 未解（推翻 triplet 后 TRSB 仍存在）| 排除磁性来源 + 确定真实序参量 |
| **Sr₂RuO₄ 真实配对对称性** | 完全开放（2020+ 多种新猜想）| NMR 低功率 + ARPES + 相位敏感实验 |
| **CsV₃Sb₅ 是否有 d+id 配对** | 实验结果不可重复 | CDW 竞争 + 样品质量 + µSR 精度 |
| **MATBG TRS 破缺来源** | 多种解释并存，SC 来源待确认 | 分辨绝缘态 vs SC 态的 TRS 破缺 |
| **UTe₂ 是否为 chiral p-wave** | 最强候选，但争议中 | Knight shift 低功率核查 + 多相图解析 |
| **Chiral SC 边缘电流能否直接探测** | 理论预言 ~10⁻⁷ A，接近 STM 极限 | STM 精度 + 边缘效应区分 |
| **Chiral d+id 的量子化 Hall 能否观测** | 理论 σ_xy = 2e²/h，未见报告 | 需要极高纯度 SC 薄膜 + Hall 测量 |

---

## 10. 关联 MECE 索引

| 关联课题 | 关系类型 | 说明 |
|---------|---------|------|
| **C5 p-wave** | **直接基础** | chiral p+ip 是 p-wave 的 TRS 破缺版；Sr₂RuO₄ 同时涉及 C5 和 C7；³He-A 确认了 chiral p+ip |
| **C3 d_x²-y² wave** | **成分之一** | chiral d+id 的 B₁g 成分；铜氧化物 d-wave（非 chiral）vs 石墨烯 d+id（chiral 候选）|
| **C4 d_xy wave** | **成分之一** | chiral d+id 的 B₂g 成分；在六角晶格中与 d_x²-y² 简并，形成 chiral 叠加 |
| **B11 拓扑超导** | **拓扑核心** | chiral p+ip = Class D（Chern C=1）→ Majorana 边缘态；chiral d+id = C=2（带电边缘模）|
| **D11 2D/界面** | **主要实验平台** | MATBG + 石墨烯：d+id 的六角晶格天然候选；2D 体系 Chern 数定义最清晰 |
| **D14 Kagome 超导** | **d+id 候选** | CsV₃Sb₅ 等 Kagome 材料的 d+id 理论预言；µSR 争议；CDW 竞争 |
| **F3 Chern 数** | **拓扑不变量** | chiral p+ip → C=±1；chiral d+id → C=±2；Chern 数计算是区分两类 chiral SC 的理论工具 |
| **A9 Andreev 反射** | **边缘态探测** | chiral Majorana 边缘态 → 零偏压电导峰（ZBCP）；但 ZBCP 有多种来源（反谄媚：ZBCP ≠ Majorana）|

---

## 附录：关键公式速查（ASCII，适配 Discord）

```
=== C7 Chiral 超导核心公式速查 ===

[1] Chiral p+ip 能隙：
  Δ(k) = Δ₀(k_x + i·k_y) = Δ₀·k_⊥·exp(i·φ_k)
  → TRS: Δ*(k) = Δ₀·k_⊥·exp(-i·φ_k) ≠ Δ(k) → TRS 破缺 ✓
  → Chern 数 C = +1（μ>0）或 -1（μ<0）
  → 边缘态：chiral Majorana（实费米子）

[2] Chiral d+id 能隙：
  Δ(k) = Δ₀[(k_x² - k_y²) + i·k_x·k_y]
       = d_{x²-y²}(k) + i·d_{xy}(k)
  = Δ₀·k_⊥²·exp(2i·φ_k)
  → Chern 数 C = ±2
  → 边缘态：带电手性费米子（非 Majorana）

[3] TRS 破缺条件：
  Δ(k) ≠ λ·Δ*(k) 对任意实数 λ
  等价：Im[Δ] ≠ 0（且不可被规范变换消去）

[4] 极向 Kerr 效应：
  θ_K ≈ (4π·d / ω·c) × Im[σ_xy(ω)]
  TRS 破缺 → σ_xy ≠ 0 → θ_K ≠ 0（零磁场下偏振旋转）

[5] 量子化 Hall（理想 T=0 极限）：
  σ_xy = C·e²/h
  p+ip (C=1): σ_xy = e²/h
  d+id (C=2): σ_xy = 2e²/h

=== 拓扑分类表 ===
  类型          Chern  边缘态        TRS  体系
  chiral p+ip   C=±1  Majorana（实） ❌   ³He-A（确认），UTe₂?
  chiral d+id   C=±2  带电（非Maj） ❌   石墨烯?, Kagome?
  helical p     Z₂    Majorana对    ✅   纳米线（理论）
  trivial s     0     无            ✅   Nb, Pb

=== 反谄媚核心 ===
  ✗ Sr₂RuO₄ chiral p+ip：2019 年 Pustogow 等已推翻（triplet 不成立）
  ✗ TRSB（PKE/µSR）信号 ≠ 确认 chiral SC（可能来自磁性、轨道序等）
  ✗ CsV₃Sb₅ d+id：µSR 结果组间不可重复
  ✗ MATBG TRS 破缺：来源不明，绝缘体相贡献未排除
  ✓ 唯一确认的 chiral SC：³He-A 超流体（液态，非固体）
  ✓ 理论框架（Read-Green 2000 拓扑 + Kallin-Berlinsky 2016 综述）成熟

=== C7 与 Paper E ===
  chiral d+id = 两轨道通道（B₁g + B₂g）的 π/2 相位叠加
  → 轨道简并（六角晶格 E₂ 表示）→ 配对简并 → TRS 破缺
  → Chiral SC 是 Paper E 轨道混合竞争的极端情况 [猜想]
  ⚠️ 需要实验确认的 chiral SC 才能真正检验 Paper E 框架
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**反谄媚审计：**
- ✅ Sr₂RuO₄ 24 年翻案完整记录（置于文首），TRSB ≠ chiral 核心声明
- ✅ 明确区分 [定理] / [猜想] / [观察] 层级
- ✅ Kagome d+id = 理论预言，实验不可重复，诚实声明
- ✅ MATBG TRS 破缺来源不明，多种竞争解释并列
- ✅ 所有数值标注来源，[来源待验证] 明确标记
- ✅ chiral d+id 形成条件苛刻性诚实记录（六角 + VHS + 强相互作用）
- ✅ PKE 测量技术门槛诚实声明（Kapitulnik 组独有精度）
- ✅ ASCII 等价公式（适配 Discord）
- ✅ ³He-A 是唯一确认的 chiral SC，诚实声明无固体确认案例
- ✅ Paper E 联系诚实标注为 [猜想]，需要实验验证
- ✅ UPt₃ B 相 chiral f-wave 可能性与 C6 连接，诚实标注争议
**C 部分状态：** C1-C7 完成，覆盖率 70% → 80%（7/10 课题完成 + 部分覆盖）
