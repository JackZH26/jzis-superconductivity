# C8. PDW（Pair Density Wave，对密度波）— 空间调制超导序参量

**MECE 编号：** C8
**关联 MECE：**
- C3（d-wave — 铜氧化物 PDW 以 d-wave 为基础；PDW 调制的是 d-wave 振幅）
- B6（CDW — PDW 数学上必然诱导 CDW at 2Q；PDW-CDW 铁律）
- B3（AFM 涨落 — PDW 的可能驱动机制；条纹相 = AFM + PDW 耦合）
- B9（RVB — Himeda-Kato-Ogata 2002 在 RVB 框架中自然出现条纹 PDW）
- B14（Mottness — 铜氧化物 PDW 的背景；欠掺杂 Mott 绝缘体 + 空穴掺杂 → 条纹不稳定性）
- H3（赝能隙 — PDW 是欠掺杂铜氧化物赝能隙的主要候选解释之一）
- H4（Fermi arc — PDW 背景下准粒子谱自然产生 Fermi arc）
- D3（铜氧化物 — PDW 理论与实验的主战场；BSCCO 最强证据）
- A1（零电阻 — PDW 态可能无长程相位相干 → 无零电阻；是超导预形成态的候选）

**层级关系：** C8 PDW 是配对对称性中最特殊的课题——它不描述 Cooper 对的角动量对称性（s/p/d/f），而是描述**序参量的实空间调制结构**。PDW 的能隙函数在实空间以有限波矢 Q 周期振荡，Cooper 对具有有限质心动量（q ≠ 0）。PDW 的核心物理意义：若赝能隙区是"无相位相干的 PDW 局部配对态"，则理解 PDW 就是理解铜氧化物相图的关键。**目前 PDW 实验证据集中于铜氧化物，以 Hamidian 2016 Nature 的 Josephson STM 为最强，但争议未止。**
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Berg-Fradkin-Kivelson 2009 PRL/Nat Phys, Hamidian 2016 Nature, Agterberg-Tsunetsugu 2008, Himeda-Kato-Ogata 2002, Fulde-Ferrell 1964, Larkin-Ovchinnikov 1965, Tranquada 1995；数值标注 [来源待验证] 处须后续核查）

⚠️ **核心诚实声明：PDW 是理论自洽的框架，但实验直接证明困难。** Hamidian 2016 的 Josephson STM 是迄今最直接的证据，但 STM 表面敏感性 + 伪影风险不能排除。PDW 与赝能隙/Fermi arc 的关联是理论预言，不是实验验证的事实。铜氧化物相图的赝能隙区是否主要由 PDW 解释，2026 年仍是开放问题。

---

## 1. 物理定义与核心思想

### 1.1 什么是 PDW？

**[定理 — PDW 的序参量定义]**

```
普通（BCS/d-wave）超导体的序参量：
  Δ(r) = Δ₀ × f(k)   （均匀振幅，f(k) 是 k 空间对称函数）
  Cooper 对质心动量 q = 0：(k↑, -k↓) 配对

PDW（Pair Density Wave）的序参量：
  Δ(r) = Δ_Q e^{iQ·r} + Δ_{-Q} e^{-iQ·r}
  
  等价形式（实版本，时间反演不变）：
  Δ(r) = 2Δ_Q cos(Q·r)    ← 振幅在实空间以波矢 Q 周期调制
  
  物理含义：
  - Cooper 对质心动量 q = ±Q ≠ 0
  - 配对粒子：(k + Q/2, ↑) 与 (-k + Q/2, ↓)
  - 能隙振幅在实空间周期性振荡，某些位置可能为零！
  - 体系在 Q 方向具有超导序的"节平面"（能隙节面）

与普通超导的本质区别：
  普通 SC：Δ 均匀（或弱调制），A1g 表示下最低能量
  PDW：Δ 调制振幅本身是主要物理，Cooper 对有有限质心动量
```

LaTeX 等价：
$$\Delta(\mathbf{r}) = \Delta_Q e^{i\mathbf{Q}\cdot\mathbf{r}} + \Delta_{-Q} e^{-i\mathbf{Q}\cdot\mathbf{r}} = 2\Delta_Q \cos(\mathbf{Q}\cdot\mathbf{r})$$

### 1.2 FFLO vs PDW：区分与联系

**[定理 — FFLO 是有磁场的 PDW 前驱]**

```
FFLO（Fulde-Ferrell-Larkin-Ovchinnikov）态：
  驱动：外磁场 H → 塞曼劈裂 h = g µ_B H / 2
  有限 q 配对波矢：q = 2h / ℏv_F（由磁场大小决定）
  物理图像：自旋不匹配 → 正常态 Cooper 对能量 → 有限 q 最优化

ASCII 等价（FFLO 波矢）：
  q_FFLO = 2h / (ℏ · v_F)    （h = Zeeman 分裂，v_F = Fermi 速度）

PDW（零场自发版本）：
  驱动：强关联相互作用（AFM 涨落、Mott 物理、条纹不稳定性）
  波矢 Q 由晶格周期性和费米面嵌套决定（不由磁场固定）
  可以在 H = 0 的情况下自发形成

关键区分：
  FFLO：需要磁场，Q 由 H 连续调节，破坏 U(1) 规范 + 平移 + 时间反演
  PDW：零场自发，Q 由晶格固定（通常 Q = π/4a 或类似有理波矢）
        破坏 U(1) 规范 + 平移对称性，时间反演可保持（实 Δ_Q）
```

### 1.3 PDW 诱导的竞争序：CDW-PDW 铁律

**[定理 — PDW 数学上必然诱导 CDW（Agterberg-Tsunetsugu 2008，Berg 2009）]**

```
PDW at Q → 诱导电荷密度调制（CDW）at 2Q

推导（[定理]）：
  电荷密度 ⟨ρ(r)⟩ ∝ |Δ(r)|² = |Δ_Q e^{iQ·r} + Δ_{-Q} e^{-iQ·r}|²
  
  展开：
  |Δ(r)|² = |Δ_Q|² + |Δ_{-Q}|² + Δ_Q Δ*_{-Q} e^{2iQ·r} + c.c.
  
  ASCII：
  ⟨ρ(r)⟩ = ρ₀ + A_{2Q} e^{2iQ·r} + c.c.
  
  其中 A_{2Q} ∝ Δ_Q · Δ*_{-Q}（PDW 序参量的二次谐波）

PDW-CDW 铁律（Berg-Kivelson）：
  PDW at Q → CDW at 2Q（必然共存，数学必然）
  反推不成立：CDW at 2Q ≠ PDW at Q（CDW 可以独立存在）
  → 看到 CDW，不能断言 PDW；但有 PDW，必有 CDW！

X 射线看到 CDW at 2Q：
  这是 PDW 的间接信号，但不是直接证据（CDW 也可以原生存在）
  真正区分需要 Josephson STM 直接测量 Δ(r) 的空间分布
```

### 1.4 赝能隙的 PDW 解释

**[猜想 — Berg-Fradkin-Kivelson 2009 Nat Phys]**

```
铜氧化物欠掺杂区（p < p_optimal）的赝能隙谜题：
  现象：T* > T_c 以下能谱有能隙，但没有长程 SC 序
  问题：这个能隙来自什么？

PDW 解释（[猜想]）：
  假设：在 T_c < T < T* 区间，存在局部 PDW 配对（Cooper 对有限 q 配对）
  这些 Cooper 对：
    ✅ 有有限振幅 Δ_Q（局部配对存在）
    ❌ 没有相位相干（∴ 没有 Meissner 效应，没有零电阻）
    → 等效于"不超导的预形成 Cooper 对"

  为什么 PDW（而非均匀 SC 局部涨落）？
    PDW 的有限 q 配对与条纹相相容（条纹 = PDW + SDW/CDW）
    均匀 SC 涨落（q=0）在欠掺杂区受 Mott 绝缘体抑制
    PDW 的调制结构与欠掺杂区的非均匀性（条纹、CDW）自然匹配

Fermi arc 的 PDW 解释（[猜想]）：
  PDW 背景下准粒子谱出现额外嵌套（影子带）：
  保留节点方向（|k|=k_F 处 |Δ_Q|=0）的 Fermi arc
  → Fermi arc 是 PDW 序参量节点方向的费米面遗留 [来源待验证：具体计算文献]
```

---

## 2. 历史关键节点

| 年份 | 事件 | 层级 | 来源 |
|------|------|------|------|
| **1964** | **Fulde & Ferrell**：外磁场下有限 q 配对（FFLO-FF 版）→ SC 能量与正常态能量竞争 | [定理，奠基] | Fulde & Ferrell 1964 Phys. Rev. 135, A550 |
| **1965** | **Larkin & Ovchinnikov**：独立推导 FFLO-LO 版（驻波形式 cosQr），完整 FFLO 框架建立 | [定理，奠基] | Larkin & Ovchinnikov 1965 Sov. Phys. JETP 20, 762 |
| **1995** | **Tranquada et al.**（LSCO x=1/8 条纹相）：中子散射发现电荷/自旋条纹共存，x=1/8 处 Tc 被抑制 → 条纹与 SC 竞争 | [观察，条纹先驱] | Tranquada et al. 1995 Nature 375, 561 |
| **2002** | **Himeda, Kato & Ogata**：VMC 计算（t-J 模型）发现 RVB 框架中条纹超导态稳定 → PDW 在 RVB 中的理论地位 | [猜想，RVB框架] | Himeda et al. 2002 PRL 88, 117001 [来源待核查卷号] |
| **2008** | **Agterberg & Tsunetsugu**：完整分析 PDW 数学结构，严格推导 CDW at 2Q 是 PDW at Q 的二次谐波（PDW-CDW 铁律）| [定理，数学奠基] | Agterberg & Tsunetsugu 2008 Nat Phys 4, 639 [来源待核查] |
| **2009a** | **Berg, Fradkin & Kivelson** PRL 102, 247002（"Striped superconductor"）：PDW 相图的系统性理论，包括 PDW + 均匀 SC + CDW 竞争 | [定理/猜想，理论里程碑] | **Berg, Fradkin & Kivelson 2009 PRL 102, 247002** |
| **2009b** | **Berg, Fradkin & Kivelson** Nat Phys（PDW 解释铜氧化物赝能隙 + Fermi arc）：PDW 作为统一描述框架 | [猜想，重要综合] | Berg et al. 2009 Nat Phys 5, 830 [来源待核查] |
| **2016** | **Hamidian et al.**（Josephson STM + BSCCO）：Josephson STM 直接测量 BSCCO 中 Δ(r) 的空间调制，发现 8a₀ 周期 PDW 信号 | [观察，**最强实验证据**] | **Hamidian et al. 2016 Nature 532, 343** |
| **2019** | **Agterberg et al.** 综述：PDW 从理论到实验的系统综述，总结现有证据和争议 | [综述] | Agterberg et al. 2019 Annu. Rev. Condens. Matter Phys. 11 [来源待核查] |
| **2020** | **Du et al.**：进一步 STM 证据（铜氧化物中 PDW）[来源待验证] | [观察，待核查] | Du et al. 2020 Science [来源待验证：卷号页码] |
| **2021+** | **Li, Wang 等系列工作**：更多 STM 数据支持 PDW 在铜氧化物中的存在 [来源待验证] | [观察，待核查] | [多篇，来源待验证] |
| **2024+** | **镍酸盐 PDW 讨论**：理论预言 La₃Ni₂O₇ 等镍酸盐中可能存在 PDW [来源待验证] | [猜想，纯理论] | [来源待验证] |

⚠️ **FFLO 实验状态（2026）：** 尽管 FFLO 理论 1964/1965 年建立，固体中直接实验证据至今有争议。重费米子 CeCoIn₅（H ∥ ab + 低温）被认为是最强 FFLO 候选 [来源待验证]。铜氧化物中磁场诱导 FFLO 证据仍有争议。

---

## 3. 数学框架

### 3.1 序参量的多 Q 叠加结构

**[定理 — PDW 的一般序参量（多 Q 叠加）]**

LaTeX：
$$\Delta(\mathbf{r}) = \sum_{\mathbf{Q}} \Delta_{\mathbf{Q}} e^{i\mathbf{Q}\cdot\mathbf{r}}$$

ASCII：
```
多 Q PDW 序参量：
  Δ(r) = Σ_Q Δ_Q exp(iQ·r)

单 Q PDW（时间反演保持，实版本）：
  Δ(r) = Δ_Q exp(iQ·r) + Δ_Q* exp(-iQ·r)
        = 2|Δ_Q| cos(Q·r + φ_Q)    （φ_Q = 相位）

条件：
  时间反演不变性：Δ_{-Q} = Δ_Q*（复数共轭）
  → 实振幅：Δ(r) = 2Δ_Q cos(Q·r)

双 Q PDW（如铜氧化物，Q_x 和 Q_y 方向各一个）：
  Δ(r) = Δ_{Q_x} cos(Q_x · x) + Δ_{Q_y} cos(Q_y · y)
  → "棋盘 PDW"（checkerboard PDW）
  → 诱导 CDW at 2Q_x, 2Q_y, 和 Q_x ± Q_y
```

### 3.2 Cooper 对有限质心动量

**[定理 — 与 BCS q=0 配对的对比]**

```
BCS Cooper 对配对结构：
  |k↑, -k↓⟩ 配对    ← 质心动量 q = k + (-k) = 0

PDW Cooper 对配对结构（有限 q）：
  |k+Q/2 ↑, -(k-Q/2)↓⟩ = |k+Q/2 ↑, -k+Q/2 ↓⟩ 配对
  质心动量 q = (k+Q/2) + (-k+Q/2) = Q ≠ 0

物理推论：
  PDW 态在动量空间中将两个偏离 k 和 -k 的费米面点配对
  → 需要费米面具有"嵌套特征"（k+Q/2 和 -k+Q/2 附近的态密度）
  → 欠掺杂铜氧化物的反节点（M 点）费米面嵌套 → Q ≈ (π/4a)(1,0) 等

ASCII 比较：
  BCS：  配对 (k, -k)         → q=0，均匀 SC
  FFLO： 配对 (k+q/2, -k+q/2) → q 由磁场决定
  PDW：  配对 (k+Q/2, -k+Q/2) → Q 由晶格/相互作用决定，自发
```

### 3.3 PDW 诱导的密度调制：铁律推导

**[定理（PDW-CDW 铁律）— Berg-Kivelson 2009，Agterberg-Tsunetsugu 2008]**

```
诱导 CDW 的推导（对角项）：
  ⟨ρ(r)⟩ ∝ ⟨Δ†(r)Δ(r)⟩ + Σ_n,σ ⟨c†_{n,σ}(r) c_{n,σ}(r)⟩
  
  单 Q PDW 时 Δ(r) = Δ_Q e^{iQ·r}：
  |Δ(r)|² = |Δ_Q|² e^{iQ·r} × |Δ_Q|* e^{-iQ·r} × corrections
  
  精确到二次项：
  ⟨ρ(r)⟩ = ρ₀ + A_{2Q} cos(2Q·r + φ)
  
  其中 A_{2Q} ∝ |Δ_Q|²（PDW 振幅的平方）
  
  → CDW 波矢 = 2Q（PDW 波矢的两倍）
  → CDW 振幅 ∝ |Δ_Q|²（二次项）

PDW 铁律（严格版本）：
  ✅ PDW at Q → CDW at 2Q（必然，数学推导）
  ✅ PDW at Q → SC (q=0)（通过 Δ_Q × Δ_{-Q} → s-wave 诱导）若双 Q PDW
  ❌ CDW at 2Q → PDW at Q（不必然，CDW 可以单独存在）
  ❌ SC (q=0) → PDW（不必然，均匀 SC 可以无 PDW）
```

### 3.4 Ginzburg-Landau 理论

**[猜想 — PDW 的现象学 GL 描述]**

```
PDW + CDW + SC 的 GL 自由能（Berg-Kivelson 框架）：

F = a|Δ_Q|² + b|Δ_Q|⁴ + c|∇Δ_Q|² 
  + α|ρ_{2Q}|² + β|ρ_{2Q}|⁴ + γ|∇ρ_{2Q}|²
  + f|Δ_Q|²|ρ_{2Q}|²    ← PDW-CDW 耦合项（铁律的来源）
  + g Δ_Q Δ_{-Q} Δ_0* + c.c.   ← PDW 诱导均匀 SC（若双 Q）
  + ...

ASCII 等价：
  F ≈ a|Δ_Q|² + b|Δ_Q|⁴ + c|∇Δ_Q|²
    + α|ρ_{2Q}|² + γ|∇ρ_{2Q}|²
    + f |Δ_Q|² |ρ_{2Q}|²
    + [Δ_Q × Δ_{-Q} → Δ_0 耦合项]

关键系数的物理含义：
  a < 0：PDW 相不稳定性（相变条件）
  f > 0：PDW 和 CDW 协同（促进共存）
  g：PDW-均匀 SC 转化率（双 Q PDW 态自动诱导均匀 SC 成分）

相图预测（[猜想]）：
  欠掺杂区（p << p_opt）：纯 PDW 态（无均匀 SC）
  优化掺杂附近（p ≈ p_opt）：均匀 SC 主导（PDW 为扰动）
  T* < T < T_c：预形成 PDW（无相位相干，赝能隙来源）
```

### 3.5 FFLO 波矢公式

**[定理 — FFLO 态的有限 q 由磁场决定]**

```
FFLO 配对波矢（Fulde-Ferrell 1964，线性近似）：

q_FF = 2h / (ℏ v_F)    ← Fulde-Ferrell 版（行波）
q_LO = 4h / (ℏ v_F)    ← Larkin-Ovchinnikov 版（驻波，π倍差异）[来源待验证：系数精确值]

ASCII：
  q ≈ 2 × (g μ_B H) / (ℏ v_F)

其中：
  h = g µ_B H / 2（塞曼劈裂能量）
  v_F = 费米速度
  H = 外加磁场
  g ≈ 2（自由电子 g 因子）

FFLO 存在条件（Chandrasekhar-Clogston 极限附近）：
  H 接近但略低于 Pauli 极限 H_P：
  H_P = Δ_0 / (√2 µ_B)    ← Pauli 极限（泡利顺磁极限）
  
  在 H ≈ (0.7-0.9) H_P 范围内 FFLO 相稳定（[猜想，材料依赖]）
```

---

## 4. 实验识别方法

### 4.1 Josephson STM — 最强判据

**[观察 — Hamidian 2016 的突破]**

```
Josephson STM 原理：
  将超导 STM 探针（SC tip）对准超导样品
  Josephson 电流 I_J ∝ |Δ_tip × Δ_sample(r)|（配对振幅直接乘积）
  
  空间分辨测量：
  I_J(r) = I_0 |Δ_sample(r)| sin(φ)
  
  → 直接测量 Δ(r) 的实空间振幅分布！
  → 这是区分 PDW（Δ(r) 调制）和 CDW（ρ(r) 调制）的最直接方法

Hamidian 2016 的关键结果（BSCCO，Bi₂Sr₂CaCu₂O₈）：
  样品：欠掺杂 BSCCO（p ≈ 0.12）
  测量：超导 Nb 针尖 + 低温 STM（T ≈ 1.9 K）[来源待核查：实验温度]
  发现：dI/dV(r, ω) 显示 8a₀（约 1.56 nm）周期的调制 [来源：Hamidian 2016 Nature 532, 343]
  Josephson 电流 I_J(r) 同样显示 8a₀ 周期 → 证明是配对密度（而非电荷密度）调制！
  
  信号在 T_c 以下增强 → 与 SC 转变耦合（非纯 CDW 伪影）
  信号在优化掺杂样品中减弱，欠掺杂最强 → 与 PDW 相图相符

⚠️ Josephson STM 的局限性：
  (a) 表面敏感（STM 仅探测几层）→ 体态 PDW 可能不同
  (b) BSCCO 天然解理面 = 表面重构 → 表面 PDW 可能不代表体态
  (c) 超导针尖的 Josephson 信号可能受磁通影响
  (d) 8a₀ 调制与 CDW 的"意外重合"不能完全排除 [来源待验证：反驳文章]
```

### 4.2 标准 STM/STS — dI/dV 图像

```
常规 STM 方法（Hamidian 2016 同文）：
  dI/dV(r, ω = Δ_gap) 图像：在能隙能量附近的隧穿谱
  → 若 Δ(r) 有周期调制 → 隧穿谱的局域 gap 振荡
  
  → 傅里叶变换：FT[dI/dV(r)] 出现 Q_PDW 峰
  → Q_PDW ≈ 2π/(8a₀) = π/(4a₀)（对 BSCCO）[来源：Hamidian 2016]

⚠️ STM 区分 PDW vs CDW 的困难：
  CDW 也会在 dI/dV 中产生调制（通过能带折叠影响局域 DOS）
  普通 STM 无法区分 Δ(r) 调制（PDW）vs ρ(r) 调制（CDW）
  → 必须用 Josephson STM（上面 4.1）才能直接区分！
```

### 4.3 X 射线衍射 — 间接证据

```
X 射线衍射识别 PDW-CDW 铁律产物：
  若 PDW at Q 存在 → CDW at 2Q → X 射线衍射出现 2Q 峰
  
  铜氧化物观测：
  YBCO 中 CDW at Q ≈ (0.3, 0) 的 X 射线峰（Keimer 等 2015 综述）[来源待核查：具体卷号]
  若这个 CDW 由 PDW 诱导：则 PDW at Q/2 ≈ (0.15, 0)
  
  ⚠️ 关键区分困难：
  X 射线看到 CDW at 2Q → 可能来自 PDW（间接）
                         → 也可能直接来自电荷-声子耦合（CDW 原生）
  → X 射线只是 PDW 间接指针，不是充分证据
```

### 4.4 ARPES — 影子带（Shadow Bands）

```
PDW 在 ARPES 中的信号：
  PDW 的波矢 Q → 布里渊区折叠（类似 CDW 效果）
  → 出现"影子带"（shadow band）：在 k 和 k+Q 处同时有谱重
  
  但与 CDW 影子带区分困难（两者均来自 Q 折叠）
  
  PDW 特征：
  能带折叠 + 能隙调制 → 在 k = Q/2 处出现额外能隙特征
  → 这与 CDW 的能隙开口（在 k_F 和 k_F + Q 处）位置略有不同 [来源待验证：理论计算]
```

### 4.5 中子散射 — PDW + SDW 协同

```
PDW 与磁性的协同（条纹 PDW）：
  铜氧化物条纹相 = SDW（自旋条纹）at Q_s + CDW（电荷条纹）at Q_c = 2Q_s
  + 可能的 PDW at Q_c（配对条纹）

中子散射（非弹性）：
  SDW 卫星峰 at Q_s → 磁序
  结合 X 射线 CDW at Q_c = 2Q_s → 条纹相结构
  → PDW at Q_c（与条纹相兼容的 PDW 假说）需要 Josephson STM 验证

LSCO x=1/8 条纹相（Tranquada 1995 Nature 375, 561）：
  中子散射 Q_s = (1/8, 0)（自旋条纹），Q_c = (1/4, 0)（电荷条纹）
  x=1/8 处 Tc 被抑制 → PDW 与 SC 相位相干竞争
  → 条纹阻止 Cooper 对的 3D 相位相干 → 无零电阻
```

---

## 5. 关键定量结果与典型材料

### 5.1 BSCCO（Bi₂Sr₂CaCu₂O₈）— PDW 最强实验证据

| 参量 | 数值 | 状态 | 来源 |
|------|------|------|------|
| PDW 波矢 | Q ≈ 2π/(8a₀) = π/(4a) | [观察] | Hamidian et al. 2016 Nature 532, 343 |
| PDW 周期 | 8a₀ ≈ 1.56 nm（a₀ = 3.8 Å）| [观察] | Hamidian et al. 2016 [a₀ 值待核查] |
| 最佳掺杂浓度 | p ≈ 0.12（欠掺杂）| [观察] | Hamidian et al. 2016 |
| Tc（相应样品）| ≈ 45-74 K（依掺杂）[来源待验证] | [观察] | [来源待验证] |
| Josephson STM 测量 | 配对密度调制（非纯电荷密度）确认 | [观察，**最强证据**] | Hamidian et al. 2016 |
| 信号随 T 变化 | T_c 以下信号增强 → SC 性质确认 | [观察] | Hamidian et al. 2016 |

```
BSCCO 的 PDW 证据链（由强到弱）：

最强：Josephson STM → I_J(r) 调制 → 直接证明配对振幅调制（非 CDW 伪影）
次强：dI/dV(r,ω) 能隙调制 → 与 SC 能隙关联的空间调制
辅助：FT 分析 → 8a₀ 周期在多个频道均出现（Q_PDW 峰一致）

⚠️ 证据链的限制：
  (1) 所有 STM 信号均来自表面（∼1-3 层）→ 体态 PDW 未直接证明
  (2) BSCCO 天然解理暴露 BiO 面 → BiO 面本身的重构可能引入 Q_PDW 信号 [来源待验证]
  (3) 8a₀ 调制在正常态（T > Tc）是否完全消失？[来源待验证：温度演化数据]
  (4) 不同 BSCCO 样品/批次的可重复性 [来源待验证]
```

### 5.2 LSCO（La₂₋ₓSrₓCuO₄）— 条纹相竞争

| 参量 | 数值 | 状态 | 来源 |
|------|------|------|------|
| 条纹相最强 | x = 1/8（空穴掺杂）| [定理] | Tranquada et al. 1995 Nature 375, 561 |
| 自旋条纹波矢 | Q_s = (1/8, 0)（reciprocal 单位 2π/a）| [观察] | Tranquada et al. 1995 |
| 电荷条纹波矢 | Q_c = (1/4, 0) = 2Q_s | [观察，PDW-CDW 铁律符合] | Tranquada et al. 1995 |
| x=1/8 处 Tc | 显著抑制（约 5-10 K vs 峰值 38 K）[来源待验证：数值] | [观察] | [来源待验证] |

```
LSCO 条纹相的 PDW 解读（[猜想]）：
  x=1/8 处：条纹稳定 → PDW 序参量有限但无 3D 相位相干
  → Cooper 对存在（局部配对）但条纹阻止 interlayer Josephson 耦合
  → 无零电阻（A1 关联：PDW 态 ≠ 零电阻 SC！）
  
  掺杂偏离 x=1/8 时：条纹溶解 → 均匀 SC 恢复
  → PDW/SC 竞争直接反映在 Tc-x 相图中
  
  ⚠️ x=1/8 抑制的其他解释：
  也可以是 CDW/条纹序直接与 SC 竞争（不需要 PDW 概念）
  PDW 是解释框架，但非唯一 [反谄媚]
```

### 5.3 YBCO（YBa₂Cu₃O₇₋δ）— X 射线 CDW 证据

```
YBCO 的 CDW 观测（[观察]）：
  优化掺杂附近：X 射线衍射发现 CDW at Q ≈ (0.3, 0) [来源待核查：具体实验]
  Keimer 综述 2015 Nature [来源待核查：卷号页码] 提及 CDW 与 SC 竞争
  
  PDW 解读（[猜想]）：
  若 CDW at 0.3 由 PDW at Q/2 = 0.15 诱导：
  → Q_PDW ≈ (0.15, 0)（比 BSCCO 的 Q_PDW 更小波矢）
  
  ⚠️ 这个解读是间接推断：
  YBCO 目前没有 Josephson STM 直接测量 [来源待验证：是否存在]
  CDW 的原生可能性（非 PDW 诱导）同样存在
```

### 5.4 CeCoIn₅ — FFLO 而非 PDW

```
CeCoIn₅（重费米子，最强 FFLO 候选）：
  Tc ≈ 2.3 K（常压）[来源待验证：精确值]
  Hc2 ∥ ab（上临界场）：约 12 T [来源待验证：精确值]
  
  FFLO 信号（[观察，争议]）：
  H ∥ ab 低温下：比热异常 + NMR 线宽 → 疑似 FFLO 态 [来源待验证]
  Q_FFLO 由磁场连续调节（区别于 PDW 固定波矢）
  
  为什么是 FFLO 而非 PDW？
  → CeCoIn₅ 在 H = 0 是普通（均匀）SC
  → FFLO 需要磁场达到接近 Pauli 极限才出现
  → PDW 是零场自发的（CeCoIn₅ 中无此证据）
  
  CeCoIn₅ 的意义：
  证明固体中有限 q 配对（FFLO 类）**原则上可能存在**
  但争议仍在（能否完全排除 vortex 晶格假象？）[来源待验证]
```

---

## 6. PDW 与其他竞争态的关系图谱

```
PDW 在铜氧化物相图中的位置（[猜想 — Berg-Fradkin-Kivelson 框架]）：

T
|
|  赝能隙区（T* < T < T_c (max)）
|  [猜想] PDW 涨落（无相位相干）
|  ← 赝能隙来源之一（可能主要来源？争议）
|
T* ─────────────────── 赝能隙临界温度
|
|  超导区（T < T_c）+ PDW + CDW 共存
|  均匀 SC（d-wave）占主导
|  ← PDW 作为"伴生"竞争态
|
T_c ─────────────────── 超导转变
|
└────────────────────────→ p（掺杂浓度）
 欠掺杂    最优掺杂    过掺杂

关键关系：
  PDW + CDW（铁律）：PDW at Q → CDW at 2Q（数学必然）
  PDW + d-wave SC：  均匀 d-wave 主导 + PDW 为调制竞争分量
  PDW + 赝能隙：     T* 以下 PDW 无相位相干 → 预形成对 → 赝能隙（[猜想]）
  PDW + Fermi arc：  PDW 背景 → 准粒子谱变形 → Fermi arc 涌现（[猜想]）
  PDW vs FFLO：      同为有限 q 配对，驱动机制不同（内禀 vs 磁场）
  PDW + SDW：        条纹相 = SDW at Q_s + CDW at 2Q_s + PDW at 2Q_s（全三者共存）

独立性区分：
  ✅ PDW 可以单独存在（无均匀 SC）→ 无零电阻的超导预形成态
  ✅ 均匀 SC 可以单独存在（无 PDW）→ 最优掺杂的均匀 d-wave
  ✅ CDW 可以单独存在（无 PDW）→ 普通电荷密度波
```

---

## 7. 关键反谄媚

### 7.1 Hamidian 2016 是最强证据，但非无争议

**[观察 — 核心反谄媚]**

```
Hamidian 2016 的强处：
  ✅ Josephson STM 直接测量配对振幅（非仅测 DOS 调制）
  ✅ 信号在 Tc 以下增强（SC 耦合确认）
  ✅ 欠掺杂样品 PDW 信号更强（与理论预言相符）

Hamidian 2016 的弱处（[观察，需要后续验证]）：
  ❌ 仅表面敏感（∼1-3 层 BSCCO 表面）
  ❌ BSCCO 解理面的 BiO 重构可能引入人工 Q 调制 [来源待验证]
  ❌ Josephson STM 技术要求极高（针尖质量、超导相位稳定性）→ 难以广泛重复
  ❌ 是否在 BSCCO 以外的铜氧化物中被独立证实？[来源待验证：截至 2026]
  ❌ 正常态（T > Tc）下 8a₀ 调制是否真正消失？[来源待验证]

结论层级：
  PDW 在 BSCCO 中存在 → [猜想，有强证据支持，但未判决]
  PDW 是铜氧化物的普遍特征 → [猜想，证据有限]
  PDW 解释赝能隙 → [猜想，竞争解释多]
```

### 7.2 PDW 是赝能隙的解释之一，非唯一

**[观察]**

```
赝能隙（H3）的竞争解释（2026 年状态，均为 [猜想]）：

(1) PDW：局部有限 q 配对 → 无相位相干 → 能谱 gap
(2) 预形成 Cooper 对（q=0）：相位涨落压制 Tc，但配对先形成
(3) CDW 竞争序：CDW 开能隙 → 类似绝缘体能隙
(4) Mott 能隙（Mottness B14）：强关联直接导致局域化能隙
(5) SU(2) 对称性（spin liquid, RVB）：自旋液体能隙（B9）

目前没有实验能够明确排除其中任意一个 [来源待验证：综述文章]

正确的层级描述：
  "PDW 是赝能隙的一种理论解释，具有一定实验支持（BSCCO STM）"
  不能说 "赝能隙由 PDW 解释"（这是过强的断言）
```

### 7.3 PDW 与 FFLO 的混淆风险

**[观察]**

```
常见混淆：
  "FFLO = PDW" × 错误！
  
  正确区分：
  FFLO：需要磁场（H ≠ 0），Q 由磁场连续调节
  PDW：零场自发（H = 0 即可），Q 由晶格/相互作用固定
  
  在磁场下：FFLO 态 + PDW 态可能同时存在，但来源不同
  
  CeCoIn₅ 的 FFLO 候选 ≠ 证明固体中存在 PDW（不同体系，不同驱动）
  铜氧化物的 PDW 候选 ≠ 证明 FFLO（无场情况下 PDW 是零场自发的）
```

### 7.4 镍酸盐 PDW：纯理论推测

**[观察]**

```
镍酸盐（D5，La₃Ni₂O₇ 等）中 PDW 讨论（2024+）：

理论动机（[猜想]）：
  镍酸盐的自旋条纹 + 双层结构 → PDW 候选（类比铜氧化物）
  部分理论计算预言 La₃Ni₂O₇ 中 PDW 稳定 [来源待验证]
  
  实验现状（2026）：
  ❌ 目前无镍酸盐 PDW 的直接 Josephson STM 实验
  ❌ 镍酸盐的 STM 测量因高压合成困难而滞后
  
  结论：镍酸盐 PDW 是 2024-2025 年的理论讨论，无直接实验支持
  → 列为 [猜想，纯理论] 级别
```

---

## 8. 与 Paper A / E 的关联

```
Paper A（两通道 Allen-Dynes 框架）：
  PDW 超出 Eliashberg 单通道框架，因为：
  (1) PDW 是非均匀态（Δ(r) 空间变化）→ 标准 Eliashberg 假设均匀 Δ
  (2) PDW 的格林函数 G(k, ω) 需要修正：Q 矢量引入非对角自能 Σ(k, k+Q)
  (3) 多通道（PDW at Q₁, Q₂, ...）→ 类似 Paper A 的多通道竞争
  
  Paper A 框架在 PDW 背景下的有效性边界：
  → Paper A 适用于均匀 SC（q=0）的多通道竞争
  → PDW（q≠0）需要额外的实空间非均匀 GL/BdG 处理
  
  连接（[猜想]）：
  Paper A 的"多通道 λ₁, λ₂"在 PDW 体系中对应"均匀 SC 通道 + PDW 通道的竞争"
  → Paper A 可能给出 PDW 是否稳定的参数范围（待正式推导）

Paper E（轨道-能隙对应原则）：
  PDW 的 Q 矢量由费米面嵌套决定，而嵌套方向由轨道选择：
  铜氧化物：d_x²-y² 轨道 → 方形费米面 → (π/4a, 0) 和 (0, π/4a) 方向嵌套 → Q_PDW
  → PDW 的 Q 矢量选择受轨道对称性约束（与 Paper E 框架一致）[猜想]
  
  PDW 对 Paper E 的挑战：
  Paper E 原则侧重于 k 空间能隙函数 Δ(k) 的轨道-对称性对应
  PDW 的主要物理是实空间调制 Δ(r)（而非 k 空间形状）
  → Paper E 需要推广到处理 q≠0 的有限质心动量配对 [待开展工作]
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026）| 主要障碍 |
|------|----------------|---------|
| **铜氧化物赝能隙是否主要由 PDW 解释？** | 无定论（竞争解释 4-5 种）| 无法用单一实验排除所有竞争解释 |
| **BSCCO PDW 是体态还是表面态？** | 未解（Josephson STM 仅测表面）| 体探针（中子 + µSR）精度不足以直接测 Δ(r) |
| **PDW 在哪些铜氧化物中存在（普遍性）？** | 仅 BSCCO 有直接证据 | Josephson STM 技术复杂，YBCO/LSCO 缺数据 |
| **镍酸盐是否有 PDW？** | 纯理论猜想 | 高压样品的 STM 测量技术障碍 |
| **PDW 能否在 Kagome 或其他体系中发现？** | 理论预言 | 缺少直接实验 |
| **PDW 的拓扑性质（PDW + d-wave 是否有拓扑非平凡相？）** | 理论探讨中 | PDW 拓扑不变量的定义需要非均匀 BdG 处理 |
| **Josephson STM 测量 PDW 的可重复性** | 数据稀少（仅 Hamidian 组）| 技术门槛极高，全球仅少数实验室有能力 |
| **PDW 与 CDW 的因果顺序** | 未解（PDW→CDW vs CDW→PDW）| 热力学 vs 动力学起源的区分极难 |

---

## 附录：关键公式速查（ASCII，适配 Discord）

```
=== C8 PDW 核心公式速查 ===

[1] PDW 序参量（实版本，时间反演不变）：
  Δ(r) = 2Δ_Q cos(Q·r)    ← 实空间振幅周期调制
  Δ(r) = Σ_Q Δ_Q exp(iQ·r)（多 Q 叠加的一般形式）

[2] Cooper 对质心动量（有限 q 配对）：
  BCS：  配对 (k↑, -k↓)         → q = 0
  PDW：  配对 (k+Q/2, -k+Q/2)   → q = Q ≠ 0
  FFLO： 配对 (k+q/2, -k+q/2)   → q 由磁场决定

[3] PDW-CDW 铁律（必然共存）：
  ⟨ρ(r)⟩ = ρ₀ + A_{2Q} cos(2Q·r)
  A_{2Q} ∝ |Δ_Q|²    ← CDW at 2Q 是 PDW at Q 的二次谐波
  → PDW at Q 必然诱导 CDW at 2Q
  → CDW at 2Q ≠ 证明 PDW at Q（CDW 可以原生）

[4] FFLO 波矢（磁场决定）：
  q_FFLO ≈ 2h / (ℏ v_F)    （h = Zeeman 劈裂，v_F = 费米速度）

[5] GL 自由能（PDW-CDW 耦合）：
  F ≈ a|Δ_Q|² + b|Δ_Q|⁴ + c|∇Δ_Q|²
    + α|ρ_{2Q}|² + γ|∇ρ_{2Q}|²
    + f |Δ_Q|² |ρ_{2Q}|²    ← PDW-CDW 耦合项（铁律来源）

[6] Josephson STM 信号（Hamidian 2016 方法）：
  I_J(r) = I_0 |Δ_sample(r)| sin(φ)
  → 直接测量 Δ(r) 的实空间振幅分布！

=== BSCCO PDW 关键数值 ===
  周期：8a₀ ≈ 8 × 3.8 Å ≈ 1.56 nm  [Hamidian 2016 Nature 532, 343]
  掺杂：p ≈ 0.12（欠掺杂，信号最强）
  方向：Q ∥ (1,0) 和 (0,1)（CuO 键方向）

=== 反谄媚核心 ===
  ✗ PDW 是确认的铜氧化物物理 → [猜想，有强证据但未判决]
  ✗ 赝能隙 = PDW → [猜想，一种解释，非唯一]
  ✗ Hamidian 2016 = 无争议 → [存在表面 vs 体态争议]
  ✗ CDW 证明 PDW → [CDW 是 PDW 的间接推论，但 CDW 可以原生]
  ✅ PDW-CDW 铁律（PDW → CDW at 2Q）是数学定理 [定理]
  ✅ FFLO 理论（有限 q 配对的存在性）是数学定理 [定理]
  ✅ Hamidian 2016 是目前最直接的 PDW 实验证据 [观察，有技术限制]
  ✅ x=1/8 条纹相 Tc 抑制是实验事实 [定理，Tranquada 1995]

=== C8 与 MECE 关联 ===
  C3（d-wave）：铜氧化物 PDW 的配对对称性以 d-wave 为基础
  B6（CDW）：PDW-CDW 铁律（数学必然的共存关系）
  H3（赝能隙）：PDW 是赝能隙的主要候选解释之一
  H4（Fermi arc）：PDW 背景下自然产生 Fermi arc 准粒子谱
  A1（零电阻）：PDW 态可以无相位相干 → 无零电阻（SC 但不超导！）
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**反谄媚审计：**
- ✅ PDW 实验证据层级诚实标注（Hamidian 2016 最强但有技术限制，明确记录）
- ✅ PDW-CDW 铁律区分严格推导（PDW→CDW 是定理，CDW→PDW 不成立）
- ✅ FFLO vs PDW 明确区分（磁场诱导 vs 零场自发）
- ✅ 赝能隙解释：PDW 是一种，非唯一，竞争解释并列
- ✅ 镍酸盐 PDW 标注为 [猜想，纯理论]，无实验支持
- ✅ CeCoIn₅ 是 FFLO 候选（非 PDW），区分明确
- ✅ 所有数值标注来源，[来源待验证] 明确标记
- ✅ x=1/8 Tc 抑制的多种解释并列（非强行 PDW 解读）
- ✅ ASCII 等价公式（适配 Discord，无 LaTeX 渲染依赖）
- ✅ Paper A/E 的联系诚实标注为 [猜想]
**C 部分状态：** C1-C8 完成，覆盖率 80% → 90%（8/10 课题完成）
