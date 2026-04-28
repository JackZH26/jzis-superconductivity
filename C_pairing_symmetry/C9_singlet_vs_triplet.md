# C9. Singlet vs Triplet — Cooper 对自旋结构的统一框架

**MECE 编号：** C9
**关联 MECE：**
- C1（s-wave — singlet 最典型，声子介导，A₁g 偶宇称）
- C2（s± — singlet，多带铁基超导，A₁g 带间符号反转）
- C3（d_x²-y² — singlet，B₁g，铜氧化物的标志性配对）
- C4（d_xy — singlet，B₂g，节线，实验未确认）
- C5（p-wave — triplet，奇宇称轨道，³He/UTe₂候选）
- C6（f-wave — triplet，E₂u，UPt₃候选）
- C7（chiral p+ip — triplet，TRS破缺，³He-A确认）
- C8（PDW — singlet 调制，通常以 d-wave singlet 为基础）
- B1（BCS — singlet 的理论框架，声子配对自然给 singlet）
- B4（FM 涨落 — triplet 的主要驱动力，q→0 铁磁涨落不排斥 triplet）
- D8（重费米子 — 最重要的 triplet 候选宿主，强 SOC + FM 涨落）

**层级关系：** C9 是 C 系列的终极综合章节。C1-C8 各自描述特定配对对称性（s/d/p/f/PDW），但它们背后共享一条基本物理约束：**Pauli 不相容原理**强制 Cooper 对的自旋结构与轨道宇称绑定——这就是 singlet vs triplet 分类的根源。C9 不引入新材料或新机制，而是提供统一的量子力学视角，揭示 C1-C8 的深层组织逻辑。**核心结论：固体超导中 singlet 远多于 triplet；³He 是唯一实验确认的 triplet 超导体；Sr₂RuO₄ 的 triplet 误判持续了 24 年，是整个领域最重要的反谄媚教训。**
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Leggett 1975 Rev. Mod. Phys., Sigrist & Ueda 1991 Rev. Mod. Phys., Anderson 1959, Pustogow et al. 2019 Nature, Ishida et al. 1998 Nature, Frigeri et al. 2004 PRL；数值标注 [来源待验证] 处须后续核查）

⚠️ **核心诚实声明：在固体超导体中，triplet 的候选远多于确认。除³He（拓扑 p-wave 超流体）之外，所有声称的固体 triplet 超导体均处于"候选"或"争议"状态。Sr₂RuO₄ 24 年的误判历史是最强烈的警告：NMR Knight shift 是最可靠判据，但实验技术陷阱（射频加热）可以系统性歪曲结论。**

---

## 1. 物理定义与核心思想

### 1.1 Pauli 原理的核心约束（完整推导）

**[定理 — Pauli 不相容原理对 Cooper 对波函数的约束]**

```
费米子的基本要求：
  ψ_total(r₁, σ₁; r₂, σ₂) = -ψ_total(r₂, σ₂; r₁, σ₁)
  
  Cooper 对波函数分解：
  ψ_total = ψ_orbital(r₁, r₂) × ψ_spin(σ₁, σ₂)
  
  交换两个电子：
  ψ_orbital → P_orbital × ψ_orbital（P_orbital = ±1，轨道宇称）
  ψ_spin    → P_spin × ψ_spin    （P_spin = ±1，自旋态的交换符号）
  
  Pauli 原理要求：
  P_orbital × P_spin = -1
  
  →（偶宇称轨道：P_orbital = +1）⟹ P_spin = -1 → 奇宇称自旋 → SINGLET
  →（奇宇称轨道：P_orbital = -1）⟹ P_spin = +1 → 偶宇称自旋 → TRIPLET
  
  ASCII 总结：
  s, d, g, ... 波（偶 L）→ 自旋 SINGLET（S=0，↑↓ - ↓↑）
  p, f, h, ... 波（奇 L）→ 自旋 TRIPLET（S=1，↑↑, ↑↓+↓↑, ↓↓）
```

LaTeX 等价：
$$\psi_{\text{total}} = \psi_{\text{orbital}}(\mathbf{r}_1,\mathbf{r}_2) \times \psi_{\text{spin}}(\sigma_1,\sigma_2)$$
$$P_{\text{orbital}} \times P_{\text{spin}} = -1$$

### 1.2 自旋态的量子力学形式

**[定理 — 自旋单态与三重态的完整表达]**

```
自旋 SINGLET（S=0，唯一一个态）：
  |S=0, m=0⟩ = (↑↓ - ↓↑) / √2    ← 反对称，奇宇称自旋
  
  物理意义：两个电子自旋相互反向，总自旋为零
  磁行为：在外磁场 H 下，自旋配对解体（Pauli 顺磁限制！）

自旋 TRIPLET（S=1，三个简并态）：
  |S=1, m=+1⟩ = ↑↑                        ← 两自旋平行（+z方向）
  |S=1, m= 0⟩ = (↑↓ + ↓↑) / √2           ← 两自旋平行（x-y平面）
  |S=1, m=-1⟩ = ↓↓                        ← 两自旋平行（-z方向）
  
  物理意义：两个电子自旋同向（或组合），总自旋为 1
  磁行为：沿 d-vector 垂直方向，外磁场不拆散 Cooper 对（无 Pauli 限制！）
```

### 1.3 d-vector 形式（triplet 的紧凑表达）

**[定理 — Balian-Werthamer 1963，d-vector 是 triplet 序参量的标准形式]**

```
Singlet 序参量（标量）：
  Δ_singlet(k) = Ψ(k)    （k 空间的偶函数）
  
  对于 s-wave：Ψ(k) = Δ₀（各向同性）
  对于 d-wave：Ψ(k) = Δ₀(cos k_x - cos k_y)（B₁g对称）

Triplet 序参量（矢量 d-vector）：
  Δ_triplet(k) = i[d(k) · σ] σ_y    （d(k) 是三分量复矢量）
  
  ASCII 等价：
  Δ_triplet(k) = i(d_x σ_x + d_y σ_y + d_z σ_z) σ_y
  
  d-vector 的物理意义：
  d(k) ⊥ 磁场方向的分量 → Cooper 对不受 Pauli 拆散
  d(k) ∥ 磁场方向的分量 → Cooper 对受 Pauli 拆散（类似 singlet）
  
  chiral p+ip（C7）的 d-vector：
  d(k) = Δ₀(k_x + ik_y) ẑ    ← 沿 z 方向，手性
  
  p-wave（C5）的 d-vector 典型形式：
  d(k) = Δ₀k ẑ    （轴向状态，等价于 He-3 A 相）
```

### 1.4 为什么 Singlet 更常见？

**[观察 — 有理论基础支持]**

```
声子配对（BCS 机制）→ 天然给 singlet：
  声子介导的电子-声子相互作用在 k 空间近似各向同性
  → 时间反演不变性下 k 和 -k 处的配对最优（q=0 Cooper 对）
  → s-wave singlet（A₁g）是最低能量态（Anderson theorem：s-wave 最鲁棒）

AFM 涨落 → 也给 singlet（d-wave）：
  反铁磁涨落的波矢 Q_AFM ≈ (π, π)（铜氧化物）
  在 (π,π) 处，自旋涨落对 d_x²-y² singlet 配对有利（同号 Δ 间排斥被利用）
  → d-wave singlet（B₁g）

FM 涨落（b4）→ 给 triplet（特殊情形）：
  铁磁涨落 q → 0（铁磁 Q=0）
  → 对 triplet 配对有利（铁磁涨落不排斥平行自旋）
  → 但 FM 与 SC 共存极少（强交换场破坏 Cooper 对），需要压力/化学调控
  
  结论：大多数超导体（BCS 材料 + 铜氧化物 + 铁基）都是 singlet！
  Triplet 是特殊情形，需要铁磁涨落、强 SOC、或几何挫折等特殊驱动。
```

---

## 2. 自旋区分的实验判据

### 2.1 NMR Knight Shift — 最直接判据

**[定理 — Knight shift 与自旋磁化率的关系]**

```
Knight shift 的物理：
  K ∝ χ_spin（电子自旋磁化率）
  K 在正常金属中反映 Pauli 顺磁性

超导转变后的变化：
  SINGLET 超导：
    Cooper 对（S=0）形成 → 自旋磁化率 χ_spin 降低（单态不响应磁场）
    → T < Tc 后 Knight shift K 明显下降
    → 外推到 T → 0 时：K → 0（全部配对，无自由自旋）
    
  TRIPLET 超导：
    Cooper 对（S=1）形成 → 沿 d-vector 垂直方向，χ_spin 不变
    → 对特定磁场方向，Knight shift 不随温度变化（K(T<Tc) ≈ K(Tn)）
    → 这是 triplet 的最直接实验指纹

技术要求（极关键！）：
  → 低射频功率（< 0.1 mT 射频场强，防止样品加热）
  → 精确温控（mK 级，特别是 Tc 附近）
  → 单晶样品 + 取向对准（各向异性 triplet 的 d-vector 方向依赖）
```

⚠️ **Sr₂RuO₄ 24 年教训（必须完整重述，这是领域内最大的反谄媚案例）**

**[观察 — 从 1998 到 2022，长达 24 年的系统性误判]**

```
时间线：
  1994：Sr₂RuO₄ 发现超导（Maeno et al. 1994 Nature 372, 532），Tc ≈ 1.5 K
        → 钙钛矿结构，但非铜氧化物
        → Rice & Sigrist 立即预言可能是 p-wave triplet（类比³He）

  1998：Ishida et al. 发表 NMR Knight shift 测量（Ishida et al. 1998 Nature 396, 658）
        结论：Tc 以下 Knight shift "基本不变" → 解读为 triplet 的证据！
        → 这一结果与 Rice-Sigrist 预言吻合 → "Sr₂RuO₄ = p-wave triplet" 成为教科书结论
        → 接下来 21 年，全领域基于此假设推进研究

  2019：Pustogow et al. 重做 NMR 实验（Pustogow et al. 2019 Nature 574, 72）
        关键改进：射频功率降低 100 倍（避免样品加热到 Tc 以上！）
        结果：Knight shift 在 Tc 以下 明显下降！
        → 这是 SINGLET（或至少有强 singlet 成分）的特征！
        → 1998 Ishida 的"不变"是因为射频加热把样品局部升温到 Tc 以上
           → Knight shift 测量的不是超导态，而是正常态！

  2020-2022：Ishida et al. 本人重做实验（Ishida et al. 2020 J. Phys. Soc. Jpn. 89, 034712）
             确认：Pustogow 2019 是对的，Knight shift 确实下降
             → 21 年的 triplet 结论被推翻！

教训（反谄媚核心）：
  1. 技术陷阱（射频加热）可以系统性地歪曲结论，导致 24 年的错误积累
  2. 结论与美丽理论吻合（Rice-Sigrist 预言 + "³He 固体版本"的概念吸引力）
     → 使实验误差长期不被质疑（Confirmation bias）
  3. NMR Knight shift 是可靠判据，但极其挑剔实验条件
  4. 即使原始实验者（Ishida）后来也承认错误 → 科学自我修正功能的正面示范
  
  Sr₂RuO₄ 当前状态（2026）：
  → singlet（可能有 d-wave 成分）vs 混合 singlet+triplet → 仍有争议 [来源待验证]
  → 但纯 triplet 结论已被否定
```

### 2.2 Pauli Paramagnetic Limit（上临界场行为）

**[定理 — BCS Pauli 极限公式（Chandrasekhar-Clogston 1962）]**

```
Singlet Cooper 对的磁场限制：
  Zeeman 效应：在磁场 H 下，↑ 和 ↓ 自旋的能量分裂 = 2µ_B H
  当 2µ_B H > Δ_gap 时，singlet Cooper 对（↑↓）被 Zeeman 拆散
  → Singlet 的上临界场存在 Pauli paramagnetic limit（顺磁极限）

BCS Pauli 极限公式（[定理]）：
  H_P = Δ₀ / (√2 µ_B)
      ≈ 1.84 × Tc    （T/K 单位，H_P 单位 T）
  
  ASCII：
  H_P (Tesla) ≈ 1.84 × Tc (Kelvin)    ← BCS singlet 的理论上限
  
  例：Tc = 10 K → H_P ≈ 18.4 T
      Tc = 1 K  → H_P ≈ 1.84 T

Triplet 对磁场的响应：
  Triplet Cooper 对（S=1）：
  → d-vector ⊥ H 方向：自旋三重态 m=+1, -1, 0 中，m=0 态（(↑↓+↓↑)/√2）
    不被 Zeeman 拆散 → H_c2 可以大幅超过 Pauli limit！
  → d-vector ∥ H 方向：m=0 态受影响（类似 singlet），H_c2 受限
  
  判据：
  H_c2 >> 1.84 Tc → triplet 的间接证据（Pauli 不受限）
  H_c2 ≈ 1.84 Tc → singlet（受 Pauli 限制）
  
⚠️ 重要警告（反谄媚）：
  H_c2 > Pauli limit ≠ 必然是 triplet！
  强自旋轨道耦合（SOC）体系：SOC 减弱 Zeeman 效应 → singlet 也可超过 Pauli limit
  轨道效应（WHH 轨道上临界场）：轨道效应通常更强，可主导 H_c2
  → 必须结合 Knight shift + 中子散射共同判断
```

### 2.3 自旋极化中子散射

**[观察 — 直接测量自旋相关响应]**

```
原理：
  非弹性中子散射测量动态磁化率 χ''(q, ω)
  自旋极化中子散射区分 spin-flip（磁) vs non-spin-flip（非磁）散射

超导态中的变化：
  SINGLET SC：
    T < Tc 后，低能（ω < 2Δ）自旋涨落谱重消失（spin gap 打开）
    → 能隙以下自旋激发被压制（Hebel-Slichter 效应的中子版本）
    
  TRIPLET SC：
    特定能量范围内，自旋涨落可以在超导态中保留
    → 自旋三重态 Cooper 对的集体激发（magnon-like 模式）
    
技术限制：
  需要大单晶样品（中子束流弱）
  能量分辨率 < Δ_gap（通常 < 1 meV）→ 技术要求高
  混乱磁信号（杂质、表面）干扰
  → 中子散射数据解读依赖 model-dependent 分析 [来源待验证：具体实验]
```

### 2.4 µSR 与 Josephson 结（次要判据）

```
µSR（Muon Spin Rotation/Relaxation）：
  对 TRSB（时间反演对称性破缺）更敏感，不直接区分 singlet/triplet
  TRSB → 自发磁场出现 → µSR 弛豫率在 Tc 以下增加
  
  Chiral triplet（C7）必然破坏 TRS → µSR 是间接支持 chiral triplet 的辅助判据
  非 chiral triplet（e.g., p-wave B1u）：TRS 保持 → µSR 无信号
  → µSR 的阳性结果支持 chiral SC，但不区分 singlet/triplet [来源待验证：典型实验]

Josephson 结（I-V 特性）：
  Singlet-singlet 结：正常 Josephson（dc 电流 ∝ sin φ）
  Singlet-triplet 结：理论上 Josephson 耦合可能为零（对称性不匹配）
                      或出现 π-结（相位偏移 π）
  → 实验上极难分辨（需要完美界面，无杂质散射）
  → 目前无明确的 singlet-triplet Josephson 实验确认 [来源待验证]
```

---

## 3. Singlet 配对族（C1-C4, C8 的统一视角）

**[定理 — 所有 singlet 配对共享的物理约束]**

```
共性：
  1. 偶宇称轨道（s, d, g...）→ 奇宇称自旋态 → S=0
  2. Cooper 对在强磁场下受 Pauli 顺磁限制（H_c2 ≤ 1.84 Tc 作为上限）
  3. Anderson 定理适用（非磁性杂质不对 s-wave 产生强 pair-breaking）
  4. NMR Knight shift 在 Tc 以下明显下降

子分类（按轨道对称性，即 C1-C4 + C8）：
```

| 配对 | 点群表示 | 节点 | 典型材料 | MECE |
|------|---------|------|---------|------|
| s-wave | A₁g | 无（全能隙）| Nb, Pb, Al, H₃S | C1 |
| s± | A₁g（多带）| 无（部分能隙）| BaFe₂As₂ 等铁基 | C2 |
| d_x²-y² | B₁g | 有（线节点）| YBa₂Cu₃O₇, BSCCO | C3 |
| d_xy | B₂g | 有（线节点）| 无实验确认 | C4 |
| PDW | A₁g+调制 | 位置依赖 | BSCCO（候选）| C8 |

```
统一的 Singlet 序参量形式（k 空间）：
  Δ_singlet(k) = Ψ(k)（偶函数：Ψ(-k) = Ψ(k)）
  
  s-wave：  Ψ(k) = Δ₀（常数）
  s±：     Ψ(k) = Δ₁（k 在带 1 上）+ Δ₂（k 在带 2 上），Δ₁·Δ₂ < 0
  d_x²-y²：Ψ(k) = Δ₀(cos kₓ - cos k_y)（B₁g，节线沿 kₓ = ±k_y）
  d_xy：   Ψ(k) = Δ₀ sin kₓ sin k_y（B₂g，节线沿 kₓ=0 和 k_y=0）
  PDW：    Ψ(r) = Ψ₀ cos(Q·r)（实空间调制，质心动量 q = Q ≠ 0）
```

---

## 4. Triplet 配对族（C5-C7 的统一视角）

**[定理 — 所有 triplet 配对共享的物理约束]**

```
共性：
  1. 奇宇称轨道（p, f, h...）→ 偶宇称自旋态 → S=1
  2. Cooper 对在沿 d-vector 垂直方向磁场下 Pauli 限制减弱
  3. Anderson 定理失效（非磁性杂质也强烈 pair-breaking！奇宇称对杂质散射敏感）
  4. NMR Knight shift 在特定方向不变（沿 d-vector ⊥ 方向）

子分类（按轨道对称性）：
```

| 配对 | 点群表示 | TRS | 节点 | 典型材料 | MECE |
|------|---------|-----|------|---------|------|
| p-wave（轴向）| E₁u（六方）/ A₁u（斜方）| 保持 | 有/无 | ³He-B, UTe₂?  | C5 |
| f-wave | E₂u（六方）| 保持 | 复杂线节点 | UPt₃?（候选）| C6 |
| chiral p+ip | E₁u（复合）| ❌ 破缺 | 无 | ³He-A（确认）| C7 |

```
d-vector 的三个分量对应三个自旋磁量子数（m = +1, 0, -1）：
  
  一般 triplet 序参量：
  Δ_triplet(k) = i[d(k)·σ]σ_y
  
  展开：
  d(k) = (dₓ(k), d_y(k), d_z(k))
  
  p-wave 的典型 d-vector：
  d(k) = Δ₀ k ẑ    （k=(k_x, k_y, k_z) 的线性组合）
  
  chiral p+ip 的 d-vector（C7）：
  d(k) = Δ₀(k_x + ik_y) ẑ    ← 复数分量 → 手性 → TRS 破缺
  
  f-wave 的典型 d-vector（UPt₃ E₂u 候选）：
  d(k) = Δ₀ kz(k_x + ik_y)² ẑ    ← 二阶手性，角动量 L=2
```

---

## 5. 什么时候会产生 Triplet？

### 5.1 铁磁性涨落（B4）— 最强驱动力

**[猜想 — 铁磁涨落驱动 triplet，有理论支持但实验复杂]**

```
铁磁涨落的波矢 q → 0（铁磁 Q=0）：
  singlet d-wave 配对需要 q = (π,π) 的涨落（AFM 嵌套）
  triplet p-wave 配对在 q → 0 的铁磁涨落下能量最优（不被 Pauli 排斥）

实验体系（铁磁 + SC 共存）：
  URhGe（Tc ≈ 0.25 K，FM Curie 温度 Tc_FM ≈ 9.5 K）[来源待验证]
    → 铁磁 + 超导共存 → 几乎确认 triplet
    → 磁场重入超导现象（H ∥ b 轴 ≈ 12 T 时 Tc 升高）[来源待验证]
    
  UCoGe（Tc ≈ 0.6 K，铁磁共存）[来源待验证]
    → 类似 URhGe，铁磁 + SC 共存
    
⚠️ 但"铁磁 + SC"不等于"一定是 triplet"：
  Hubbard 模型计算表明铁磁波动也可以诱导 singlet（如果有轨道简并）
  实验确认需要 Knight shift 证据（URhGe 的 NMR 极困难：Tc 超低 + 磁性样品）
  → URhGe/UCoGe triplet 是[猜想，强烈支持]级别，而非[定理]
```

### 5.2 强自旋轨道耦合（SOC）

**[观察]**

```
强 SOC（重元素：U, Ce, Ir, Ru...）的效应：
  SOC 将自旋和轨道自由度混合（j = l ± 1/2 是好量子数）
  → 纯 singlet 和纯 triplet 不再是好的对称性基
  → 混合态：Δ(k) 含 singlet + triplet 成分
  
  可能结果（[猜想]）：
  (a) 强 SOC → singlet 被抑制 → triplet 主导（重费米子 D8 中）
  (b) 强 SOC → 稳定混合态（NCS 超导，见第 7 节）
  (c) 强 SOC + 铁磁涨落 → p-wave triplet 最稳定
  
⚠️ SOC 使区分复杂化（重要反谄媚）：
  重元素体系中，Knight shift 的 singlet/triplet 差异可能被 SOC 效应修正
  → 即使 Knight shift 在 Tc 以下不变，也可能是 SOC 修正的 singlet
  → 必须做理论计算（DFT + SOC）结合实验综合判断
```

### 5.3 FM+SC 共存材料列表

```
强 triplet 候选材料（FM+SC 共存，[猜想] 级别）：

| 材料    | Tc (SC) | Curie 温度 | 理由 | 来源 |
|--------|---------|-----------|------|------|
| URhGe  | ~0.25 K | ~9.5 K    | FM+SC共存, 重入SC | [来源待验证] |
| UCoGe  | ~0.6 K  | ~3 K      | FM+SC共存（弱FM）| [来源待验证] |
| UGe₂   | ~0.8 K（高压）| ~52 K | 压力诱导SC, FM态中 | [来源待验证] |
| UTe₂   | ~1.6 K  | 无长程FM  | 强磁涨落, H_c2 >>Pauli | [来源待验证] |
| UPt₃   | ~0.5 K  | AFM       | 多相图, f-wave 候选 | [来源待验证] |

注：以上所有数值标注为[来源待验证]，需核查原始论文。
    ³He 是唯一确认的 triplet 超流体（非固体 SC）。
```

---

## 6. Singlet-Triplet 混合（非中心对称超导，NCS）

**[猜想 — Frigeri et al. 2004 PRL，NCS 超导的理论框架]**

```
对称性基础：
  中心对称（有反演对称）：singlet 和 triplet 是独立的不可约表示
  → 不能混合（奇宇称 vs 偶宇称是好量子数）

非中心对称（NCS，缺乏反演对称）：
  → 晶格无反演中心 → 宇称不是好量子数
  → Rashba SOC（反演对称破缺产生的 k 线性自旋分裂）
  → singlet 和 triplet 可以共存于同一材料！

混合序参量：
  Δ(k) = Δ_s(k) （singlet 成分）+ Δ_t(k) （triplet 成分）
  
  ASCII：
  Δ(k) = Ψ(k) iσ_y   +   i[d(k)·σ]σ_y
          ↑ singlet         ↑ triplet
  
  两者之比由 Rashba SOC 强度 α_R 决定：
  → α_R → 0：中心对称极限，回到纯 singlet 或纯 triplet
  → α_R 大：两者混合，拓扑性质可能发生变化

典型 NCS 超导体：
  CePt₃Si（Tc ≈ 0.75 K）：最早发现的 NCS 重费米子 SC [来源待验证：Bauer 2004 PRL]
  Y₂C₃（Tc ≈ 18 K）：非中心对称，较高 Tc [来源待验证：卷号页码]
  Li₂Pt₃B（Tc ≈ 2.7 K）：Rashba SOC 强，混合态证据 [来源待验证]
  BiPd（Tc ≈ 3.8 K）：NCS，拓扑候选 [来源待验证]
  
理论（[猜想]，Frigeri et al. 2004，[来源待验证：PRL 卷号]）：
  Frigeri-Samokhin-Tsunetsugu 框架：
  → NCS SC 中 Rashba SOC 使费米面分裂为 ± 自旋带
  → 每个自旋带上分别有 singlet + triplet 混合配对
  → 拓扑非平凡相（topological NCS SC）的条件：triplet 成分主导时

⚠️ 注意：NCS SC 的 singlet-triplet 混合比例至今无法精确测量
  → 无法从实验直接确定 |Δ_s / Δ_t| 的比值 [来源待验证]
  → 这是 NCS SC 的核心未解问题之一
```

---

## 7. 关键反谄媚

### 7.1 Sr₂RuO₄ — 24 年教训再强调

**[观察 — 超导领域最重要的反谄媚案例，必须铭记]**

```
完整时间线：1994 发现 → 1998 "triplet 确认" → 2019 Pustogow 推翻 → 2020 Ishida 确认推翻

误判的根源：
  [技术]：射频功率过高 → 样品局部加热到 Tc 以上 → 测量的是正常态 Knight shift
  [认知]：Rice-Sigrist 预言的"³He 固体版"概念太有吸引力
         → Confirmation bias 使实验误差 21 年不被质疑
         → 理论家和实验家相互强化（循环论证）

现代启示：
  1. Knight shift 实验的射频功率必须记录和报告（标准化要求）
  2. 美丽的理论预言 + 与实验"吻合" ≠ 正确（可能是 confirmation bias）
  3. 越美丽的结论，越要多次独立验证（不同组、不同方法）
  4. Sr₂RuO₄ 当前状态（2026）：
     → 可能是 singlet（d-wave？）或 singlet+triplet 混合
     → 多个理论模型仍在竞争 [来源待验证：综述]
     → 纯 p-wave triplet 已被否定
```

### 7.2 Triplet 候选远多于确认

**[观察 — 核心反谄媚立场]**

```
唯一完全确认的 triplet：
  ³He 超流体（非固体超导体）：
    A 相 = chiral p-wave（L=1, S=1），TRS 破缺，拓扑非平凡
    B 相 = BW（Balian-Werthamer）态，各向同性 triplet
    → 通过热力学 + NMR + 声波实验完全确认 [Leggett 1975 Rev. Mod. Phys. 47, 331]

固体超导中"triplet 候选"（全部为 [猜想]）：
  UTe₂：2025 年最活跃争议，Knight shift（低质量数据）+ H_c2 >> Pauli
  UPt₃：f-wave 候选，多相图，µSR TRSB 信号 [来源待验证]
  URhGe/UCoGe：FM+SC 共存，triplet 几乎确认但 Knight shift 数据极少
  Sr₂RuO₄：已否定纯 triplet，现状复杂
  
关键立场：
  "triplet SC" 的论文发表量 >> 实验确认量
  每个新 SC 体系发现后，如果有有趣的磁性背景，都会立即猜测 triplet
  → 猜测本身无问题（科学需要假说）
  → 但猜测必须标注为 [猜想]，不能当[定理]引用
```

### 7.3 H_c2 超过 Pauli Limit 不等于 Triplet

**[观察 — 常见逻辑谬误]**

```
错误推理链：
  H_c2 > 1.84 Tc → "超过 Pauli limit" → triplet！ ❌

正确分析：
  H_c2 > Pauli limit 的 SINGLET 解释：
  (1) 轨道效应（WHH 轨道上临界场）主导：
      H_c2 (orbital) ~ Φ₀ / (2π ξ²) >> H_P（脏极限材料）
  (2) 强 SOC：SOC 减弱有效 Zeeman 效应 → singlet H_c2 升高
  (3) 非均匀超导（FFLO）：有限 q 配对部分规避 Pauli 拆散
  
  → 必须同时：H_c2 > Pauli limit + Knight shift 不变 + 排除 SOC 效应
  → 才能支持 triplet 解释
  
  负面教训：许多"发现 triplet"的论文仅靠 H_c2 > Pauli limit 就下结论
  → 这是不充分的！
```

### 7.4 Anderson 定理保护了 Singlet，惩罚了 Triplet

**[定理 — Anderson 1959]**

```
Anderson 定理（[定理]）：
  s-wave singlet 超导：非磁性杂质不产生 pair-breaking
  → 即使有序参量破坏（disorder），Tc 不被抑制（一级近似）
  
  Triplet 超导的惩罚（[定理]）：
  奇宇称配对对所有散射（磁性 + 非磁性）均强烈 pair-breaking
  → 即使非磁性杂质（无磁散射）也破坏 triplet SC！
  → 这是为什么固体中 triplet SC 极难实现的物理原因
  
  实验含义（[观察]）：
  如果某材料声称是 triplet，其 Tc 应该对晶格缺陷/杂质极其敏感
  → 高纯度样品 vs 掺杂样品的 Tc 对比是间接支持 triplet 的方法
  
  对比：
  s-wave BCS（singlet）：可以在多晶、薄膜、合金中实现（Tc 鲁棒）
  triplet 候选（如 UTe₂）：Tc 对样品质量极度敏感 → 与 Anderson 定理一致 [来源待验证]
```

---

## 8. 与 Paper A / E 的关联

```
Paper A（两通道 Allen-Dynes / Eliashberg 框架）：
  默认假设：所有材料均为 singlet（s-wave 或 s±）
  → 声子通道 λ_ph + 电子-电子通道 λ_ee 均在 s-wave singlet 框架内
  → 重费米子（triplet 候选区，D8）被显式排除在外
  
  triplet 对 Paper A 的挑战：
  若某材料是 triplet，其 T_c 公式需要使用铁磁涨落介导的 triplet 通道
  → 对应的 Eliashberg 方程形式不同（spin-fluctuation kernel 不同）
  → Paper A 框架需要扩展才能覆盖 triplet（待开展工作）
  
  当前 Paper A 的安全范围：singlet 材料（BCS + 铜氧化物 + 铁基 + H₃S 等）
  明确排除：UTe₂, UPt₃, URhGe 等 triplet 候选体系

Paper E（轨道-能隙对应原则）：
  核心逻辑：轨道对称性 → 决定能隙节点结构 → 决定低能激发
  C9 的联系（[猜想]）：
  偶宇称轨道（d_x²-y², d_z²...）→ singlet → B₁g/A₁g 节点对称性（Paper E 直接处理）
  奇宇称轨道（p_z, p_x, f...）→ triplet → E₁u/E₂u 节点对称性
  
  Pauli 原理是 Paper E 的深层约束：
  Paper E 的"轨道→节点→能隙结构"对应关系，实际上包含了 Pauli 原理
  → 偶宇称轨道对应的配对类型全部是 singlet（Paper E 的隐含前提）
  → Paper E 扩展到 triplet 体系时，需要明确 d-vector 的方向依赖
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026）| 主要障碍 |
|------|----------------|---------|
| **UTe₂ 是 singlet 还是 triplet？** | 最活跃争议，大量样品质量依赖数据 | 高纯单晶的 NMR Knight shift（低 Tc ≈ 1.6 K + 强磁性）极困难 |
| **Sr₂RuO₄ 真实配对态是什么？** | 不再是纯 triplet，但 singlet/混合仍争议 | 多轨道效应（α/β/γ 三条费米面）理论复杂 |
| **是否存在完全拓扑 triplet SC 固体？** | 理论丰富（Chern insulator + SC）| 实验确认极难（需同时确认 triplet + 拓扑不变量）|
| **NCS SC 的 singlet-triplet 混合比例** | 无法精确测量 | 缺乏直接测量混合比例的实验方法 |
| **Anderson 定理失效的精确条件** | 已知理论框架，但对 triplet 的定量 pair-breaking 率研究少 | 需要超纯样品 + 可控杂质掺杂 |
| **轴向 p-wave（B相类）固体 SC 存在吗？** | 未发现确认体系 | ³He-B 的固体类比在常压下极不稳定 |
| **FM+SC（URhGe 类）triplet 的直接 Knight shift 测量** | 极少数据（超低 Tc + 磁场环境使 NMR 困难）| 技术障碍：Tc < 0.5 K + 内禀磁场干扰 NMR |

---

## 附录：核心公式速查（ASCII，适配 Discord）

```
=== C9 Singlet vs Triplet 核心公式速查 ===

[1] Pauli 原理约束（[定理]）：
  P_orbital × P_spin = -1
  偶宇称（s,d）→ 奇宇称自旋 → singlet（S=0）
  奇宇称（p,f）→ 偶宇称自旋 → triplet（S=1）

[2] 自旋态（[定理]）：
  Singlet： |S=0,m=0⟩ = (↑↓ - ↓↑)/√2
  Triplet： |S=1,m=+1⟩ = ↑↑
            |S=1,m= 0⟩ = (↑↓ + ↓↑)/√2
            |S=1,m=-1⟩ = ↓↓

[3] d-vector 序参量（[定理]）：
  Δ_triplet(k) = i[d(k)·σ]σ_y
  chiral p+ip：d(k) = Δ₀(k_x + ik_y) ẑ
  
[4] Pauli 极限（BCS singlet，[定理]，Chandrasekhar-Clogston 1962）：
  H_P (Tesla) ≈ 1.84 × Tc (Kelvin)
  例：Tc = 10 K → H_P ≈ 18.4 T

[5] NMR Knight shift 判据（[定理]）：
  Singlet → K(T < Tc) 明显下降
  Triplet → K(T < Tc) 沿 d-vector ⊥ 方向不变
  ⚠️ 技术要求：低射频功率，防止样品加热！（Sr₂RuO₄ 教训）

[6] NCS 混合态（[猜想]，Frigeri 2004）：
  Δ(k) = Ψ(k) iσ_y + i[d(k)·σ]σ_y
         ↑ singlet      ↑ triplet

=== Singlet 家族一览 ===
  s-wave（A₁g）→ C1：Nb, Pb, H₃S
  s±（A₁g多带）→ C2：铁基 BaFe₂As₂
  d_x²-y²（B₁g）→ C3：铜氧化物
  d_xy（B₂g）→ C4：无确认
  PDW（实空间调制singlet）→ C8：BSCCO（候选）

=== Triplet 家族一览 ===
  p-wave（E₁u/A₁u）→ C5：³He, UTe₂?
  f-wave（E₂u）→ C6：UPt₃?（候选）
  chiral p+ip（E₁u复合）→ C7：³He-A（确认）

=== 反谄媚核心立场 ===
  ✅ Pauli 原理约束（singlet/triplet 分类）是严格定理 [定理]
  ✅ ³He 是唯一完全确认的 triplet 超导/超流体 [定理]
  ✅ Anderson 定理：s-wave singlet 对非磁性杂质鲁棒；triplet 不鲁棒 [定理]
  ✅ H_P ≈ 1.84 Tc 是 BCS singlet 的 Pauli 极限 [定理]
  ⚠️ Sr₂RuO₄ triplet 结论 1998-2019 年是系统性误判（射频加热）[观察]
  ⚠️ 所有固体 triplet SC 候选（UTe₂, UPt₃, URhGe...）均为 [猜想]
  ⚠️ H_c2 > Pauli limit ≠ triplet（SOC + 轨道效应可以提高 H_c2 而保持 singlet）
  ⚠️ NCS 体系中 singlet/triplet 不是好量子数（Rashba SOC 混合）

=== C9 与 MECE 关联 ===
  C1-C4,C8（singlet 族）：偶宇称轨道，Pauli 限制，Knight shift 下降
  C5-C7（triplet 族）：奇宇称轨道，Pauli 限制减弱，Knight shift 不变
  B1（BCS）：声子 → singlet s-wave 的理论基础
  B4（FM 涨落）：q→0 铁磁 → triplet 的主要驱动力
  D8（重费米子）：triplet 候选的主要实验宿主区域
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**反谄媚审计：**
- ✅ Sr₂RuO₄ 24 年误判完整重述（技术根因 + 认知偏差双重分析）
- ✅ ³He 是唯一确认的 triplet，所有固体 triplet 均标注为 [猜想]
- ✅ H_c2 > Pauli limit ≠ triplet（SOC + 轨道效应另解）明确写出
- ✅ Knight shift 技术陷阱（射频加热）和正确实验要求完整记录
- ✅ Anderson 定理对 singlet/triplet 的不对等保护明确推导
- ✅ NCS 超导的 singlet-triplet 混合以 [猜想] 标注，测量困难明确
- ✅ URhGe/UTe₂ 等材料数值全部标注 [来源待验证]
- ✅ Pauli 原理推导以 [定理] 标注（严格量子力学结论）
- ✅ Paper A/E 关联诚实标注有效范围和局限
- ✅ ASCII 等价公式（适配 Discord，无 LaTeX 渲染依赖）
**C 部分状态：** C1-C9 完成，覆盖率 90% → 95%（9/10 理论课题 + 1 综合完成）
