# C5. p-wave 配对对称性 — 奇宇称三重态，以及 Sr₂RuO₄ 的 24 年教训

**MECE 编号：** C5
**关联 MECE：**
- C9（Singlet vs Triplet — p-wave 的自旋结构是 triplet，S=1，是 triplet 配对的代表体系）
- C3（d_x²-y² wave — Sr₂RuO₄ 2019 年后更可能是 singlet d-wave；两者争议史是本文核心）
- C7（Chiral 配对 — chiral p+ip 是拓扑超导的核心模型；C5 是 C7 的物理基础）
- B4（FM 自旋涨落 — triplet 配对的主要驱动机制，铁磁涨落稳定 triplet 通道）
- B11（拓扑超导 — chiral p+ip 是 AZ 分类 D 类 Chern=±1 拓扑超导的原型模型）
- D8（重费米子 — UPt₃、URhGe、UCoGe 是固体 p-wave/triplet 候选体系）
- D12（拓扑超导候选 — Kitaev chain 是 1D p-wave 模型，chiral p+ip 是 2D 拓扑 SC 原型）
- A9（Andreev 反射 — triplet 超导的 Andreev 谱与 singlet 不同；ZBCP 与 Majorana 关联）

**层级关系：** C5 是奇宇称（p 轨道）三重态（triplet）配对的代表，是拓扑超导（C7/B11）的物理起点；³He 是唯一经过实验确认的 p-wave 超流体，**固体超导体中至今无确认的 p-wave 材料**
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Maeno 1994、Rice-Sigrist 1995、Pustogow 2019、Leggett 1975 等原始文献；Sr₂RuO₄ 争议史为本文重点）

⚠️ **核心诚实声明：固体超导体中没有任何材料被实验判决性地确认为 p-wave（奇宇称 triplet）配对态。** ³He 超流体的 A 相（chiral p+ip）是唯一确认的 p-wave 系统。Sr₂RuO₄ 曾经 24 年被认为是 chiral p-wave，2019 年被推翻。本文档忠实记录这段历史，这是物理学中"共识不等于真理"的最生动案例之一。

---

## 1. 物理定义与核心思想

### 1.1 奇宇称配对：Pauli 原理的要求

**[定理 — Pauli 原理]**

Cooper 对总波函数必须是反对称的（费米统计）：

$$\Psi_{\rm total}(\mathbf{k}, \sigma_1, \sigma_2) = \Psi_{\rm orbital}(\mathbf{k}) \times \Psi_{\rm spin}(\sigma_1, \sigma_2)$$

奇宇称 × 奇自旋 = 偶（反对称）：

```
宇称（轨道）   自旋       总波函数   允许？
─────────────────────────────────────────
  偶（s,d）  singlet(S=0)  奇×偶=偶   ✅ → s-wave, d-wave
  偶（s,d）  triplet(S=1)  偶×奇=奇   ❌
  奇（p,f）  singlet(S=0)  奇×偶=奇   ❌
  奇（p,f）  triplet(S=1)  奇×奇=偶   ✅ → p-wave, f-wave
```

**p-wave 的 k 空间奇宇称（[定理]）：**
```
p-wave 定义：Δ(-k) = -Δ(k)   ← k 空间奇对称

对比 s-wave：Δ(-k) = +Δ(k)   ← 偶对称
对比 d-wave：Δ(-k) = +Δ(k)   ← 偶对称
```

**结论：** p-wave 配对强制要求自旋三重态（S=1），因此 p-wave ≡ triplet 配对，两者不可分割。

### 1.2 d-vector 形式：三重态配对的矩阵表示

**[定理]** 三重态配对（S=1）由 d-vector（也写作 d-向量）描述：

$$\hat{\Delta}(\mathbf{k}) = i[\mathbf{d}(\mathbf{k}) \cdot \boldsymbol{\sigma}]\sigma_y$$

ASCII:
```
Δ(k) = i [d(k)·σ] σ_y      （triplet 配对矩阵，2×2 自旋空间）

其中：
  d(k) = (d_x(k), d_y(k), d_z(k)) — d-vector，奇宇称
  σ = (σ_x, σ_y, σ_z) — Pauli 矩阵
  σ_y = [[0,-i],[i,0]]
```

**展开形式（明确矩阵元素）：**
```
          [ -d_x + id_y    d_z       ]
Δ(k) =   [                           ]
          [  d_z          d_x + id_y ]

三个分量对应三重态的 m_S = +1, 0, -1 子态：
  |↑↑⟩ ∝ d_x + id_y
  |↓↓⟩ ∝ -d_x + id_y
  (|↑↓⟩ + |↓↑⟩)/√2 ∝ d_z
```

**物理意义：**
```
|d(k)|² = 准粒子能隙的大小：|Δ(k)| = |d(k)|

d-vector 方向 = "断对方向"（d 所在方向的自旋分量不配对）：
  d ⊥ z → z 方向自旋量子化轴，d 在 xy 平面
  d ∥ z → d 沿 z，z 分量的 m_S=0 对不配对
```

### 1.3 p-wave 的具体形式

**最简单的 p-wave（p_x 波，[定义]）：**
```
d(k) = Δ₀ k_x ẑ    （指向 z 轴的 p_x 波）

能隙：|Δ(k)| = Δ₀|k_x|
节线：k_x = 0（kyz 平面，线节点）
```

**chiral p-wave（p+ip，[定义 — 拓扑超导原型]）：**

$$\mathbf{d}(\mathbf{k}) = \Delta_0(k_x \hat{x} + ik_y \hat{y})$$

ASCII:
```
d(k) = Δ₀(k_x x̂ + i k_y ŷ)    chiral p+ip（手性 p 波）

能隙：|Δ(k)|² = Δ₀²(k_x² + k_y²) = Δ₀² k²  → 各向同性（无节点！）
角动量：m = ±1（沿 z 轴旋转获得相位 ±2π → Chern 数 C = ±1）

特征：
  - 全能隙（no nodes）— 类似 s-wave，但有拓扑！
  - 破时间反演（TRS breaking）：chiral p+ip ≠ chiral p-ip 是不同时间反演态
  - 边界 chiral Majorana mode（Chern=1 的拓扑边态）
```

**helical p-wave（p±ip，DIII 类，[定义]）：**
```
d(k) = Δ₀(k_x x̂ ± k_y ŷ)（两个 Chern 数为 ±1 的叠加）

物理：
  - 时间反演不变（TRS preserved）
  - DIII 拓扑类（T² = -1, C 对称性）
  - 有 helical Majorana 边态（成对，非手性）
  - 与 B11 中的 DIII 类关联
```

**节点结构对比（[定理]）：**
```
chiral p+ip：无节点（各向同性能隙）
             → 指数穿透深度（类 s-wave 低温行为）
standard p_x：线节点（k_x = 0 平面）
             → 线性穿透深度（类 d-wave 低温行为）
³He-B 相：    无节点（Balian-Werthamer 对称态）
             → 全能隙，各向同性
```

---

## 2. 历史关键节点（Sr₂RuO₄ 教训是重点）

### 2.1 ³He 超流体：p-wave 的奠基（确认案例）

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **1972** | **Osheroff-Richardson-Lee** 发现 ³He 超流体（A 相和 B 相），后获 1996 年 Nobel 物理学奖 | [定理，实验确认] | Science 1972; DOI: 10.1103/PhysRevLett.28.885 |
| **1975** | **Leggett** 完整理论框架：³He 是 p-wave triplet 超流，用 d-vector 描述 A/B 相；B 相 = Balian-Werthamer（BW）态 | [定理，理论+实验一致] | Rev. Mod. Phys. 47, 331 (1975) |
| **1975+** | NMR 实验直接确认 d-vector 方向：³He-A 相 = chiral p+ip（d ∥ 轨道面），³He-B 相 = 球对称 triplet | [定理，实验] | 多篇，综述见 Vollhardt-Wölfle 1990 |

**³He 的确认标准（p-wave 判决性证据）：**
```
(1) NMR Knight shift：T_c 以下不降（triplet 特征，singlet 会降）
(2) NMR d-vector 各向异性：直接测定 d-vector 方向
(3) 超流密度张量各向异性：A 相 ≠ B 相
(4) Andreev-Bashkin 效应
→ 以上四项共同判决，没有任何一项可以被系统误差解释
```

**结论：³He 超流体是 p-wave triplet 的唯一已确认实例（固体超导体中零）。**

### 2.2 Sr₂RuO₄：24 年的 p-wave 共识与 2019 年翻案

**[这是 C5 文档的核心：物理学史上最著名的共识被推翻案例之一]**

**阶段一：发现（1994）**

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **1994** | **Maeno 等** 发现 Sr₂RuO₄ 超导，T_c = 1.5 K，钙钛矿层状结构（类铜氧化物但无 Cu）| [定理，实验] | **Nature 372, 532 (1994)** |

T_c = 1.5 K 是 Sr₂RuO₄ 的实验值，来源：[Maeno 1994 Nature 372, 532]（无需标注"待验证"）

**阶段二：p-wave 预言与共识建立（1995-2019）**

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **1995** | **Rice & Sigrist** 预言 Sr₂RuO₄ 是 chiral p-wave（类比 ³He-A 相）：Ru 的自旋涨落为铁磁性（FM），FM 涨落驱动 triplet | [猜想 → 后被推翻] | **J. Phys.: Condens. Matter 7, L643 (1995)** |
| **1998** | **Ishida 等** NMR Knight shift 实验：T_c 以下 Knight shift **不降**（沿 ab 面），解释为 triplet 支持 | [观察 → 后被发现是实验误差] | **Nature 396, 658 (1998)** |
| **1998** | **Luke 等** µSR 实验：发现自发内磁场（T < T_c），证明时间反演对称性破缺 → 支持 chiral 配对 | [观察 — 至今仍存在，但与现状矛盾] | PRL 80, 1272 (1998) |
| **2001** | **Lupien 等** 热导率各向异性实验：旋转磁场下振荡 → 节点存在 → 表面"支持"线节 p-wave | [观察，现解释有争议] | PRL 86, 5986 (2001) |
| **2004** | **Nelson 等** µSR 实验再次确认自发磁场（时间反演破缺）→ 进一步"支持"chiral p-wave | [观察 — 至今未解决] | PRB 69, 020504 (2004) |
| **2006** | **Kidwingira 等** Josephson 结：动态磁化行为暗示域结构（chiral 域）→ "支持"chiral | [观察 — 解释存疑] | Science 314, 1267 (2006) |
| **2012** | **Jang 等** 半量子磁通实验（半整数 h/4e 磁通）：解释为 chiral 态证据 | [猜想 — 解释有争议] | Science 331, 186 (2011) |

**⚠️ 注意：** 上述 1995-2019 的"支持证据"没有一项是判决性的。每项都有替代解释，但当时学界普遍倾向 p-wave。

**阶段三：推翻（2019）**

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **2019** | **Pustogow 等** 用**更低射频功率**重做 Knight shift 实验：发现 T_c 以下 Knight shift **明显下降** → singlet 信号！ | [定理级实验，推翻共识] | **Nature 574, 72 (2019)** |

**Pustogow 2019 的关键发现（[定理 — 推翻 1998 Ishida 结果]）：**
```
问题所在：1998 Ishida 等的实验使用了过高的射频（RF）功率
          → 样品被 RF 加热到 T > T_c
          → Knight shift 看起来"不变"是因为样品根本没有进入超导态！

更低 RF 功率（不加热样品）→ 重新测量：
  结果：T_c 以下 Knight shift 明显下降（~50%）
  → 这是 singlet 配对的标志
  → triplet 被排除（至少 triplet 不是主态）

这是一个因仪器技术误差导致的 24 年错误。
实验技术的细节（RF 功率）改变了结论。
```

**阶段四：现状（2020-2026）**

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **2020** | **Petsch 等** 极化中子散射：T_c 以下自旋磁化率下降 → singlet 支持 | [定理，实验] | Science 369, 1010 (2020) [来源待验证：Science 卷/页需二次核实] |
| **2020+** | 多个理论组重新分析：Sr₂RuO₄ 最可能是 d-wave singlet（B₁g 或 B₂g 表示）| [猜想 → 目前主流] | 多篇 PRB/PRL 2020-2024 |
| **2026** | Sr₂RuO₄ 的真实配对对称性**仍然是开放问题** | [观察] | — |

**µSR 信号的悬案（[观察 — 至今未解]）：**
```
⚠️ 大问题：µSR 看到的时间反演破缺信号（自发磁场）在 2019 年后仍然存在！
  → 1998 Luke + 2004 Nelson 的 µSR 实验结果本身没有被推翻
  → 但 singlet d-wave 不能破时间反演（除非有 d+id 混合）

这是 Sr₂RuO₄ 的核心矛盾（截至 2026）：
  Knight shift + 中子散射 → singlet
  µSR 自发磁场 → 时间反演破缺（不能是简单 singlet！）

可能的解释（均为猜想）：
  (a) 时间反演破缺来自非均匀掺杂或表面/界面效应
  (b) Sr₂RuO₄ 是 d+id（手性 singlet，破 TRS）
  (c) 极低磁场中存在微弱拓扑效应
→ 这个问题 2026 年尚无定论
```

### 2.3 其他 p-wave/triplet 候选（固体）

⚠️ 以下均为 [猜想] 层级，无判决性实验确认：

| 材料 | T_c | 证据 | 层级 | 状态 |
|------|-----|------|------|------|
| **UPt₃** | ~0.5 K | 多相 SC 相图（A/B/C 相），热导率节点，E₂u 表示 → triplet f-wave 候选 | [猜想] | 争议中；来源待验证（参考 Joynt-Taillefer Rev. Mod. Phys. 2002）|
| **URhGe** | ~0.25 K | 强磁性 SC，FM 共存 → triplet 候选；场诱导再入超导 | [猜想] | 来源：Aoki 2001 Nature 413, 613 [来源待验证] |
| **UCoGe** | ~0.6 K | FM + SC 共存，SC 沿 c 轴；Knight shift 各向异性暗示 triplet | [猜想] | 来源：Huy 2007 PRL 99, 067006 [来源待验证] |
| **UTe₂** | ~1.6 K | 2019 Science 发现；多个 Knight shift 实验支持 triplet；多相 SC 相图 | [猜想 → 目前最有希望] | 来源：Ran 2019 Science 365, 1070 |

**UTe₂ 特别值得关注（[猜想 — 当前最强候选]）：**
```
UTe₂ vs Sr₂RuO₄ 的关键区别：
  Sr₂RuO₄：Knight shift 后来被发现是实验误差（RF 加热）
  UTe₂：Knight shift 部分实验组仍显示 triplet，但不同实验组结果不一致

UTe₂ 的优势：
  (1) 多个 SC 相（至少 3 个相），提供拓扑转变的证据
  (2) U 的铀基轨道天然支持 triplet
  (3) 极高磁场下（>50T）再入超导相 → 可能 triplet

UTe₂ 的争议：
  (1) 不同实验组 Knight shift 方向依赖结论不一致
  (2) Sr₂RuO₄ 的教训警告：必须极低 RF 功率！
  (3) 样品依赖性极强（杂质/缺陷敏感）
```

---

## 3. 数学框架

### 3.1 p-wave 的完整 BdG 方程

**[定理 — Bogoliubov-de Gennes 方程，triplet 版本]**

在 Nambu 空间（含自旋），BdG Hamiltonian 为：

$$H_{\rm BdG} = \begin{pmatrix} H_0(\mathbf{k}) & \hat{\Delta}(\mathbf{k}) \\ \hat{\Delta}^\dagger(\mathbf{k}) & -H_0^T(-\mathbf{k}) \end{pmatrix}$$

ASCII:
```
H_BdG(k) = [ H₀(k)         Δ̂(k)     ]
            [ Δ̂†(k)      -H₀ᵀ(-k)   ]

其中 Δ̂(k) = i[d(k)·σ]σ_y  是 2×2 triplet 配对矩阵
```

**chiral p+ip（2D 情形）的完整 BdG：**
```
H₀(k) = (k²/2m - μ)σ₀   （正常态，二维抛物能带）
Δ̂(k) = Δ₀(k_x + ik_y)iσ_y   （chiral p+ip，d ∥ ẑ）

展开后（只看自旋向上分支，k_z = 0）：
  H_BdG = (k²/2m - μ)τ_z + Δ₀ k_x τ_x + Δ₀ k_y τ_y

其中 τ 是粒子-空穴 Nambu 空间的 Pauli 矩阵
→ 这正是 Read-Green (2000) 的 p+ip BdG 方程
```

### 3.2 chiral p-wave 的拓扑数

**[定理 — Chern 数]**

对于 2D chiral p-wave（半填充，μ > 0 情形）：

$$C = \frac{1}{2\pi} \int_{\rm BZ} d^2k \, \Omega(\mathbf{k}) = \pm 1$$

ASCII:
```
Chern 数 C = ∓1  （对应 p±ip，±1 取决于手性）

积分（Berry 曲率 Ω 的 BZ 积分）：
  Ω(k) = -2 Im [⟨∂_{kx}u|∂_{ky}u⟩]

物理后果（[定理]）：
  C = ±1 → 边界有 ±1 条 chiral Majorana 边态
  Majorana 零模（在涡旋中心）→ 非 Abel 任意子
  零模满足 γ† = γ（Majorana 条件）
```

**相变条件（p+ip，[定理]）：**
```
弱拓扑（trivial）：μ < 0  → C = 0（真空，无边态）
强拓扑（non-trivial）：μ > 0  → C = ±1（chiral Majorana 边态）
相变点：μ = 0（节点在 k = 0 打开，拓扑相变！）

这是 Kitaev chain（1D 版）的 2D 类比：
  Kitaev chain：μ/t < -1（trivial），μ/t > -1（topological）
```

### 3.3 singlet vs triplet 配对矩阵对比

**[定理 — 完整对比]**

```
singlet（偶宇称轨道，S=0）：
  Δ_singlet(k) = Δ_s(k) · iσ_y    （标量 × 矩阵）
  Δ_s(-k) = +Δ_s(k)               （偶宇称）
  条件：Δ_s(k) = Δ_s(-k)

  例：s-wave: Δ_s = Δ₀（常数）
      d-wave: Δ_s = Δ₀(cos k_x - cos k_y)

triplet（奇宇称轨道，S=1）：
  Δ_triplet(k) = i[d(k)·σ]σ_y    （向量 × 矩阵）
  d(-k) = -d(k)                   （奇宇称！）
  能隙：|Δ(k)|² = Tr[Δ†Δ]/2 = |d(k)|²

  例：p-wave（chiral）: d(k) = Δ₀(k_x + ik_y)ẑ
      p-wave（helical）: d(k) = Δ₀(k_x x̂ + k_y ŷ)
      f-wave：奇宇称的更高次，如 d(k) ∝ k_x(k_x²-3k_y²)
```

**Knight shift 的 singlet/triplet 判据（[定理]）：**
```
物理：在外加磁场 H 下，Knight shift K ∝ χ_spin（自旋磁化率）

singlet（s-wave 或 d-wave）：
  T < T_c → Cooper 对中自旋对齐到 ±1/2 → 没有自由自旋 → χ 下降
  → Knight shift 在 T_c 以下急剧下降（沿所有方向）

triplet（d-vector 垂直于 H）：
  T < T_c → 自旋可以沿 H 方向对齐（d ⊥ H 时）→ χ 不变
  → Knight shift 在 T_c 以下**不变**（沿 d ⊥ H 方向）

⚠️ Sr₂RuO₄ 教训：这个判据的实验实现要求样品温度真正低于 T_c
   → 过高 RF 功率会加热样品 → 假象的"不变" → 24 年错误
```

---

## 4. p-wave 的实验识别方法

### 4.1 NMR Knight shift（最重要，最危险）

**[定理 — 原理明确]，[观察 — 实验执行极易出错]**

```
判据：
  singlet → T_c 以下 K 急剧下降（所有方向）
  triplet（d ⊥ H）→ T_c 以下 K 不变

⚠️⚠️⚠️ Sr₂RuO₄ 教训（2026 年最重要的实验教训之一）：
  问题：RF 线圈加热 → 样品 T_eff > T_c → Knight shift "不变" = 假象
  解决：极低 RF 功率 + 精确温度校准

实验要求（从 Pustogow 2019 学到）：
  (1) RF 功率：必须足够低，使样品不被加热
  (2) 独立温度计：同时监测样品实际温度
  (3) 不同 RF 功率多次测量：验证结果与功率无关
  (4) 对 UTe₂ 等新候选体系：必须强制执行以上步骤！
```

### 4.2 µSR（正电子自旋旋转）

**[观察]**

```
判据：chiral 或时间反演破缺的超导 → 自发内磁场 → µSR 频率偏移
  非零 Δ(t=0) 的 µSR 不对称 → 时间反演破缺（TRS breaking）

Sr₂RuO₄ 的 µSR 情况：
  1998 Luke + 2004 Nelson：发现自发内磁场（Δ ≈ 0.5 G）
  2019 年后：µSR 信号**仍然存在**，未被推翻

但这与 singlet 矛盾：singlet d-wave 不破 TRS（没有手性项）
→ Sr₂RuO₄ 的 µSR 问题（2026 年）：仍然未解！
```

**µSR 的限制：**
```
不能区分 p-wave 和其他破 TRS 的态（如 d+id、f+if）
只能告诉你是否有 TRS 破缺，不能告诉你具体配对对称性
```

### 4.3 穿透深度 λ(T)

```
chiral p+ip（无节点）：
  δλ(T) ∝ exp(-Δ₀/T)   ← 指数型（全能隙）
  类似各向同性 s-wave

standard p_x（有节线）：
  δλ(T) ∝ T            ← 线性（类 d-wave）
  类似 d-wave

注意：chiral p+ip 的穿透深度与 s-wave 相同！
→ 穿透深度无法区分 chiral p+ip 和 s-wave
→ 需要同时结合 Knight shift 和 µSR
```

### 4.4 比热

```
chiral p+ip：
  C_s(T→0) ∝ exp(-Δ₀/T)   ← 指数型（全能隙）

standard p_x（节线）：
  C_s(T→0) ∝ T²            ← 幂次（类 d-wave）

Sr₂RuO₄ 比热：
  早期数据暗示有节点（T² 行为）→ 与 chiral（无节点）矛盾
  → 这本身就是 1995-2019 共识中的矛盾，多数人假设是杂质效应 [来源待验证]
```

### 4.5 Josephson 效应（相位敏感）

```
triplet-singlet Josephson 结：
  角电流 I_c sin(φ) 的大小反映波函数重叠
  triplet ↔ singlet 结：
    理论：J_c 极小（自旋结构不匹配）
    实验：弱但非零（因自旋轨道耦合）

区分 triplet vs singlet 的相位实验（[猜想，未执行于固体 p-wave]）：
  原则上类比 Tsuei-Kirtley 实验（C3），但设计不同
  目前没有固体 p-wave 材料实现判决性约瑟夫森相位实验
```

---

## 5. 关键定量结果与典型材料

### 5.1 Sr₂RuO₄ — 24 年争议主角

| 参量 | 数值 | 来源 |
|------|------|------|
| T_c | 1.5 K（单晶）| [Maeno 1994 Nature 372, 532] |
| 晶体结构 | 四方 K₂NiF₄ 型（层状钙钛矿）| — |
| Fermi 面 | 三个圆柱面（α, β, γ 带，Ru 4d 轨道主导）| — |
| µSR 自发磁场 | ~0.5 G（T < T_c 内部场）| [Luke 1998 PRL] [来源待验证具体值] |
| 2019 Knight shift 变化 | ~50% 下降（T_c 以下，沿 ab 面）| [Pustogow 2019 Nature 574, 72] |

**2020-2026 Sr₂RuO₄ 现状总结（[观察]）：**
```
主流共识（截至 2026）：singlet 配对，最可能是 d-wave（B₁g 或 B₂g）

支持 singlet 的证据：
  ✅ Knight shift T_c 以下下降（Pustogow 2019）
  ✅ 极化中子散射自旋磁化率下降（Petsch 2020）
  ✅ 多项 NMR 测量（2020 年后多组）

仍然无法解释的证据：
  ❌ µSR 自发磁场（Luke 1998, Nelson 2004）仍然存在！
  ❌ 半量子磁通（Jang 2011）解释存疑

可能的解释（均为猜想）：
  [猜想] (a) singlet d+id 混合（手性 singlet，破 TRS）
  [猜想] (b) 界面效应导致 µSR 信号
  [猜想] (c) 微量杂质/掺杂引起局部 TRS 破缺

→ Sr₂RuO₄ 的配对对称性在 2026 年仍是开放问题！
```

### 5.2 ³He 超流体 — 唯一确认的 p-wave

| 参量 | ³He-A 相 | ³He-B 相 |
|------|---------|---------|
| 压力 | > 21 bar | 全范围（低压）|
| 温度 | T_c ~ 2.5 mK（21 bar）| T_c ~ 0.9 mK（0 bar）|
| 配对对称性 | chiral p+ip（L=1, S=1, J=0）| Balian-Werthamer（等各向同性 triplet）|
| d-vector | d(k) = Δ₀(k_x + ik_y)（A 相）| d = ΔR·k̂（R 是旋转矩阵，B 相）|
| 时间反演 | 破缺（chiral）| 保持（全对称）|
| 能隙 | 无节点（各向同性）| 无节点（球对称）|
| 确认证据 | NMR d-vector + 旋转实验 | NMR + 超流密度各向同性 |

来源：[Osheroff 1972 PRL 28, 885]；[Leggett 1975 Rev. Mod. Phys. 47, 331]

### 5.3 UPt₃ — 重费米子 triplet 候选（[猜想]）

```
UPt₃：T_c = 0.5 K，两个（或三个）超导相

证据：
  - 多 SC 相图（A/B/C 相，由磁场和压力分隔）→ 暗示非简并、有点/线节点的配对
  - 热导率：低温 T² 行为 → 有节点（线节点？）
  - 比热跳跃：双峰（两相变）→ E₂u 表示（2D 表示）

理论候选：E₂u（f-wave triplet）[来源：Joynt & Taillefer Rev. Mod. Phys. 74, 235 (2002)]
  f-wave = 奇宇称、L=3、triplet
  d(k) ∝ k_z(k_x + ik_y)² 或类似形式

⚠️ 注意：E₂u 指向 f-wave，不是 p-wave！UPt₃ 严格说应属 C6（f-wave），
         但其 triplet 性质与 p-wave 的 triplet 配对物理直接相关
         → 在 C5 中作为 triplet 固体 SC 的重要案例提及
```

---

## 6. p-wave 与相关配对的层级关系

| 配对 | 宇称 | 自旋 | L | 代表 | 节点 | 拓扑 |
|------|------|------|---|------|------|------|
| s-wave（C1）| 偶 | singlet | 0 | Nb, Pb | 无 | 无（标准）|
| d_x²-y²（C3）| 偶 | singlet | 2 | YBCO | 有（线）| 部分 |
| **p-wave（C5）**| **奇** | **triplet** | **1** | **³He-A** | **无（chiral）/ 有** | **✅（Chern=1）**|
| f-wave（C6）| 奇 | triplet | 3 | UPt₃? | 有 | 待定 |
| chiral p+ip（C7）| 奇 | triplet | 1 | ³He-A | 无 | ✅（Chern=1）|
| Singlet/Triplet（C9）| — | — | — | — | — | 分类框架 |

**p-wave 的独特地位：**
```
p-wave（C5）是连接以下概念的枢纽：
  B4（FM 涨落）→ triplet 配对机制
  C9（singlet/triplet 区分）→ 自旋结构
  C7（chiral p+ip）→ 拓扑延伸
  B11（拓扑 SC）→ 物理实现
  D12（拓扑候选）→ 实验搜寻

缺少 C5，整个拓扑超导概念链就没有物理起点。
```

---

## 7. Sr₂RuO₄ 教训的反谄媚总结（核心价值）

### 7.1 "24 年共识被推翻"的完整过程

**[观察 — 物理学方法论教训]**

```
时间线：
  1994 - 发现 Sr₂RuO₄（Maeno，T_c=1.5K）
  1995 - Rice-Sigrist 预言 chiral p-wave（类比 ³He）
  1998 - Knight shift "不变"（Ishida）→ triplet 支持（实为 RF 加热误差）
  1998 - µSR 时间反演破缺（Luke）→ 支持 chiral
  2001 - 热导率各向异性（Lupien）→ 表面支持节点
  2004 - µSR 再次确认（Nelson）
  2006 - Josephson 暗示域结构（Kidwingira）
  ... 24 年间：p-wave 是"教科书事实"，写入 review articles
  2019 - Pustogow 低功率 Knight shift：下降！singlet 回归！
  2020 - 中子散射确认（Petsch）
  2026 - 配对对称性仍是开放问题（µSR 未解）
```

### 7.2 为什么这么多"证据"都错了

**[观察 — 方法论分析]**

```
每一项"支持证据"的问题：

1. Knight shift（1998 Ishida）：
   错误原因：RF 加热（技术误差）
   教训：仪器功率/样品温度必须独立校准

2. µSR 时间反演破缺（1998 Luke, 2004 Nelson）：
   错误？不一定！µSR 信号本身可能是真实的
   问题：解释错误（以为 TRS 破缺 = chiral p-wave）
   现状：µSR 信号真实但无法用 singlet d-wave 解释 → 仍是谜

3. 热导率各向异性（2001 Lupien）：
   问题：节点的存在不等于 p-wave 节点（d-wave 也有节点）
   教训：单一观测无法区分多种配对对称性

4. Josephson 实验（2006 Kidwingira）：
   问题：域结构也可来自 singlet 多面体/轨道序
   教训：复杂效应的解释需要 Occam 剃刀

总结：所有这些证据都是"与 chiral p-wave 一致"而非"只有 chiral p-wave 才能解释"
→ 相关性被误认为因果性
```

### 7.3 反谄媚教训的核心

**[观察 — 适用于所有物理研究]**

```
教训 1：共识时长 ≠ 共识正确性
  24 年 = 0 证明力；24 年被推翻 ≠ 24 年错了（μSR 信号仍存在）

教训 2：积累的"证据"不一定是证据
  每一项单独的"支持"都是不完整的。量不等于质。

教训 3：技术误差可以隐藏 24 年
  射频功率——一个仪器细节——改变了一个领域的方向。
  没有人注意到，因为结论"符合预期"。

教训 4：推翻共识后，问题通常更复杂
  Sr₂RuO₄ 不是"从 p-wave 换成 d-wave 就结束了"
  → µSR 异常把问题复杂化了
  真实的物理往往比任何共识都更奇特

教训 5（适用于我们自己的研究）：
  用我们的数值/理论结果时：
  - "与预测一致"≠ 正确
  - 技术细节可以改变结论
  - 矛盾的数据是最重要的数据
```

---

## 8. 与 Paper A/E 的关联

**Paper A（多通道 Eliashberg / SMW 框架）：**
```
p-wave 体系（Sr₂RuO₄、重费米子）超出 Paper A 的多通道 singlet 框架：
  → Paper A 的 SMW 方程处理 singlet 通道（s, d wave）
  → triplet 通道需要单独的 Eliashberg 方程（triplet 自能结构不同）
  → Paper A 不能直接应用于 UPt₃、UTe₂ 等

边界明确（[观察]）：
  Paper A 框架对 p-wave 材料不适用（除非扩展到 triplet 通道）
```

**Paper E（轨道-能隙对应原则）：**
```
p-wave 在 Paper E 框架中的角色（[猜想]）：

轨道角动量 L=1（p 轨道）→ 配对 L=1（p-wave）
d-vector 与 Ru 4d 轨道的 t_{2g}（d_xy, d_xz, d_yz）的角动量关联

具体：
  Sr₂RuO₄ 的 Ru t_{2g} 三轨道 → 轨道角动量有效 L=1（类 p 轨道）
  Paper E 的轨道对应原则：L_eff=1 的 t_{2g} 轨道 → p-wave 能隙（L=1）

这是 Paper E 的一个重要测试案例：
  若 Sr₂RuO₄ 真的是 d-wave（不是 p-wave），
  则需要解释为何 L_eff=1 的 t_{2g} 轨道选择了 L=2 的配对对称性
  → 这要么推翻 Paper E，要么说明轨道对应更复杂

⚠️ 这是一个有效的预言性检验（PREDICTION），值得重视
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026）| 挑战 |
|------|----------------|------|
| **Sr₂RuO₄ 真实配对对称性** | singlet（很可能 d-wave），但 µSR 异常未解 | µSR 信号的非超导来源 vs 手性 singlet；需要场诱导 Kerr 效应等新实验 |
| **固体 p-wave 是否存在？** | UTe₂ 是最强候选，但仍是猜想 | Knight shift 不同组结果矛盾；样品质量；Sr₂RuO₄ 教训警告 |
| **UTe₂ 配对对称性** | triplet 候选，多相 SC 相图支持 | 需要低 RF 功率 Knight shift + µSR + 比热综合 |
| **chiral p+ip 在 2D 固体中** | 尚无确认 | 需要拓扑边态（chiral Majorana）的判决性实验 |
| **UPt₃ 真实对称性** | E₂u（f-wave triplet）猜想，多相支持 | 低 T_c（0.5K）限制许多实验；单晶极难制备 |
| **Paper E 轨道对应 vs Sr₂RuO₄** | 开放预言：t_{2g} L_eff=1 → p-wave 还是 d-wave？| 需要理论深化 + Sr₂RuO₄ 确定配对对称性 |
| **Kitaev chain 物理实现** | InAs 纳线 + s-wave SC 中实验进行中 | ZBCP 是 Majorana 还是 Andreev 束缚态？（争议持续 10 年+）|

---

## 10. 关联 MECE 索引

| 关联课题 | 关系类型 | 说明 |
|---------|---------|------|
| **C9 Singlet vs Triplet** | **自旋结构（最关键）** | p-wave 的 triplet 自旋结构；Knight shift 判据；d-vector 形式 |
| **C3 d_x²-y²** | **Sr₂RuO₄ 争议史** | 2019 年后 Sr₂RuO₄ 最可能是 singlet d-wave；与 p-wave 共识推翻的关键参照 |
| **C7 Chiral 配对** | **拓扑延伸** | chiral p+ip 是 C7 的物理实例；C5 是 C7 的基础 |
| **B4 FM 自旋涨落** | **triplet 配对机制** | FM 涨落稳定 triplet（p-wave）通道；Rice-Sigrist 的物理出发点 |
| **B11 拓扑超导** | **物理基础** | chiral p+ip 是 D 类拓扑 SC（Chern=1）的原型；C5 提供 BdG 基础 |
| **D8 重费米子** | **材料候选** | UPt₃、URhGe、UCoGe、UTe₂ 是 triplet 固体 SC 的最强候选 |
| **D12 拓扑超导候选** | **实验前沿** | Kitaev chain、InAs 纳线等都以 p-wave 为核心模型 |
| **A9 Andreev 反射** | **实验探针** | triplet SC 的 Andreev 谱与 singlet 不同；ZBCP 争议与 Majorana 相关 |

---

## 附录：关键公式速查（ASCII，适配 Discord）

```
=== C5 p-wave 核心公式速查 ===

[1] Pauli 原理（强制 triplet）：
  奇宇称轨道（p-wave）必须配 triplet 自旋
  Δ(-k) = -Δ(k)  ← p-wave 奇宇称定义

[2] triplet 配对矩阵（d-vector 形式）：
  Δ̂(k) = i[d(k)·σ]σ_y
  |d(k)|² = 准粒子能隙大小
  d(-k) = -d(k)  ← d-vector 奇宇称

[3] chiral p+ip（最重要特例）：
  d(k) = Δ₀(k_x x̂ + i k_y ŷ)
  能隙：|Δ(k)| = Δ₀√(k_x² + k_y²)  ← 各向同性，无节点！
  Chern 数 C = ±1  ← 拓扑超导（D 类，AZ 分类）
  边态：chiral Majorana mode

[4] helical p-wave（DIII 类）：
  d(k) = Δ₀(k_x x̂ ± k_y ŷ)
  时间反演不变，DIII 拓扑类
  边态：helical Majorana mode（成对，非手性）

[5] Knight shift 判据（关键实验，最易出错！）：
  singlet → T_c 以下 K 急剧下降（所有方向）
  triplet（d ⊥ H）→ T_c 以下 K 不变
  ⚠️ Sr₂RuO₄ 教训：RF 加热会伪造"不变"信号！

[6] chiral p+ip BdG（2D，简化）：
  H_BdG = (k²/2m - μ)τ_z + Δ₀k_x τ_x + Δ₀k_y τ_y
  拓扑相变：μ = 0（trivial: μ<0，topological: μ>0）

=== Sr₂RuO₄ 简史（24 年教训）===
  1994 发现 (Maeno, Nature 372, 532)
  1995 Rice-Sigrist 预言 chiral p-wave
  1998 Knight shift "不变" (Ishida) → 实为 RF 加热误差！
  2019 Pustogow: Knight shift 下降 → singlet！(Nature 574, 72)
  2026 仍是开放问题：µSR 异常未解

=== 反谄媚核心点 ===
  ✗ 固体超导体中零材料被确认为 p-wave
  ✗ 24 年共识 ≠ 真理（Sr₂RuO₄ 教训）
  ✗ µSR 信号真实但无法被 singlet d-wave 解释（开放问题）
  ✗ UTe₂ 是最强候选但仍是猜想（Sr₂RuO₄ 教训警告）
  ✓ ³He 超流体 A 相：唯一确认的 chiral p+ip

=== 与 C 系列其他的关系 ===
  C5（p-wave）与 C7（chiral）：C5 是基础，C7 是拓扑延伸
  C5 vs C3（d-wave）：Sr₂RuO₄ 把 C5 和 C3 绑在一起 24 年
  C5 → B11（拓扑 SC）：chiral p+ip 是拓扑 SC 的原型模型
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**反谄媚审计：**
- ✅ 核心声明：固体超导体中零材料被实验确认为 p-wave，置于文首
- ✅ Sr₂RuO₄ 24 年翻案完整记录：发现→预言→积累"证据"→推翻→现状
- ✅ µSR 未解问题诚实记录（不隐瞒当前共识的漏洞）
- ✅ RF 加热误差的具体机制如实说明（不只是"实验误差"）
- ✅ UTe₂ 作为新候选：支持与挑战都列出，不过度乐观
- ✅ 所有定量数值标注来源，[来源待验证] 明确标记
- ✅ 明确区分 [定理] / [猜想] / [观察] 层级
- ✅ Paper A/E 的边界与关联诚实记录
- ✅ ³He 是唯一确认 p-wave，固体 SC 中零案例，诚实声明
**C 部分状态：** C1-C5 完成，覆盖率 50% → 60%（5/10 课题）
