# D13. 二维半导体超导体 — TMD 单层、Ising 超导与 CDW 竞争

**MECE 编号：** D13
**关联 MECE：**
- D11（2D/界面 — BKT 和 MoS₂ 门控已覆盖；D13 聚焦半导体材料本身的超导物理）
- E3（门控调控 — 离子液体门控是 D13 的主要调控手段）
- B6（CDW — NbSe₂/TaS₂ 中电荷密度波与超导的竞争序）
- F8（BKT — Berezinskii-Kosterlitz-Thouless 相变：所有 2D 超导的共同相变机制）
- C1（s-wave — MoS₂ 门控 SC 被认为是声子介导 BCS s-wave，配对参见 C1）
- B13（平坦带 — MATBG 属于 D11/B13 的范畴，D13 专注真正的半导体材料）
- B11（拓扑超导 — MoTe₂ 作为拓扑 SC 候选，与 D12 关联）

**层级关系：** D13 是**二维半导体材料中的超导**综述。核心特征：原生为半导体或绝缘体的二维材料，通过电场门控、化学掺杂、压力等手段诱导超导。与 D11（2D/界面）的区分：D11 重点是界面处的超导机制（LAO/STO、FeSe/STO），D13 重点是二维半导体材料本身的超导物理。主要体系：TMD 单层（MoS₂、NbSe₂、WS₂、TaS₂ 等），关键物理：Ising 自旋轨道耦合（SOC）、BKT 相变、CDW 竞争序。
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Ye 2012 Science、Xi 2016 Nat Phys、Lu 2015 Science、Saito 2016 Nat Phys 等核心文献框架；数值标注来源，未精确核查项注明 [来源待验证]）

---

## 1. 物理定义与核心思想

### 1.1 什么是 2D 半导体超导体

**[定义层级 — 框架性定义；具体材料的超导机制标注层级]**

```
2D 半导体超导体（D13）的定义：

  原生态：半导体或绝缘体（无载流子，或载流子密度极低）
  诱导超导的手段：
    (a) 电场门控（Field-effect gating）— 主要手段，D13 的核心
         离子液体门控（EDLT）：可达 n₂D ~ 10¹⁴ cm⁻²（极高）
         固态背栅：调控范围较小
    (b) 化学掺杂（intercalation）：Cu 嵌层（D11/C区关联）
    (c) 压力：施加静水压力（部分体系有效）
    (d) 近邻效应（异质结）：接触 SC → 诱导（更多属于 D11）

  与 D11 的区分（关键！）：
    D11（2D/界面）：研究的是界面处的超导增强机制
      → 例：FeSe/STO 的界面增强（STO 的软声子）
      → 例：LAO/STO 界面的 2DEG 超导
    D13（2D 半导体）：研究的是二维半导体材料本身的超导物理
      → 例：MoS₂ 单层门控后的 SC（主体是 MoS₂ 的配对机制）
      → D11 已覆盖 MoS₂ 门控的基本事实，D13 深入展开超导物理

  与 D12（TSC 候选）的交叉：
    MoTe₂ 处于 D13 和 D12 的交叉（拓扑相变附近的超导）[猜想]
    NbSe₂ 单层 Ising SOC 与拓扑 SC 的潜在联系 [猜想]
    D13 专注材料本身的超导现象，TSC 候选性质参见 D12
```

### 1.2 TMD（过渡金属二硫族化合物）的特殊物理

**[TMD 晶体结构决定的对称性为 [定理]；具体物理效应为 [定理]；配对机制推论为 [猜想]]**

```
TMD 晶格结构（H 相 vs T 相）：

  H 相（蜂窝/三棱柱配位）：
    代表材料：MoS₂、MoSe₂、WS₂、WSe₂（2H 相）
    单层：D₃h 对称性，反演对称性破缺！
    导带底位于 K 和 K' 点（布里渊区角）
    
  T/1T' 相（八面体配位）：
    代表材料：TaS₂（1T 相）、MoTe₂（Td/1T' 相）
    具有不同的电子结构，涉及 CDW 和拓扑相变

  K/K' 谷的物理（H 相 TMD）[定理]：
    
    谷简并：E(K↑) = E(K'↓)（时间反演相关的简并）
    谷-自旋锁定：
      K 谷 → 主要被自旋 ↑ 电子占据
      K' 谷 → 主要被自旋 ↓ 电子占据
    物理根源：H 相单层无反演对称 → 强 Ising SOC
    
    有效哈密顿量（低能，K/K' 谷附近）：[定理，来自群论 + k·p]
    LaTeX:  H_0 = v_F (k_x \sigma_x + \tau_z k_y \sigma_y) - \mu + \lambda_I \tau_z \sigma_z
    ASCII:  H_0 = v_F*(kx*sigma_x + tau_z*ky*sigma_y) - mu + lambda_I*tau_z*sigma_z
    
    其中：
      tau_z = ±1（K/K' 谷指标）
      sigma = 自旋 Pauli 矩阵
      lambda_I = Ising SOC 强度（面外方向！）
      v_F = 费米速度

  Ising SOC 的关键效果：[定理]
    lambda_I*tau_z*sigma_z 项 → 自旋被锁定在 ±z 方向（面外）
    K 谷：↑ 自旋能量降低（或升高，取决于正负）
    K' 谷：↓ 自旋（相反）
    → 谷-自旋锁定（valley-spin locking）[定理]

  BKT 相变（F8）[定理]：
    所有真正的 2D 超导都经历 BKT 相变，而非普通相变
    2D 超导序参量 = 振幅 × 相位，振幅在 Tc 以下有限，相位有涡旋激发
    BKT Tc: 涡旋-反涡旋对解离温度
    实验判据：I-V 曲线幂律 V ∝ I^α，在 T_BKT 处 α → 3
    ASCII: V ~ I^alpha, alpha -> 3 at T_BKT  [定理]
```

---

## 2. 历史关键节点

**[历史 — 有明确来源的标注；无确切来源的标注 [来源待验证]]**

```
★★★ 2012 Ye et al.（东京大学，J. T. Ye、Y. J. Zhang 等）
  实验：离子液体 EDLT 门控 MoS₂ 单晶薄片
  结果：Tc ≈ 10.8K @ n₂D ~ 10¹⁴ cm⁻²（超导 dome 出现）
  意义：第一个 TMD 门控超导！证明半导体 TMD 可以成为超导体
  [Ye et al. 2012, Science 338, 1193]（确定）
  注：D11 已覆盖基本事实，D13 从超导物理角度深入展开

★★★ 2015 Lu et al.（东京大学 + 多机构）
  实验：离子液体门控，系统研究 MoS₂/MoSe₂/MoTe₂/WS₂ 四种 TMD
  结果：多种 TMD 均出现超导，Tc 各不相同
  重要发现：电场诱导超导的普遍性在 TMD 家族中得到验证
  [Lu et al. 2015, Science 350, 1353]（来源部分待精确核查）

★★★ 2016 Xi et al.（EPFL，X. Xi、Z. Wang 等）
  实验：机械剥离单层 NbSe₂，两端测量 + STM
  结果：
    (a) BKT 相变清晰可见（I-V 曲线 α=3），Tc（BKT）≈ 3K
    (b) 体材 NbSe₂ Tc = 7.2K → 单层降至 3K（CDW 竞争 + 2D 相位涨落）
    (c) CDW 转变温度：体材 33K → 单层 145K（CDW 大幅增强！）
  意义：最干净的 2D 超导实验，BKT 相变直接证明
  [Xi et al. 2016, Nature Physics 12, 139]（确定）

★★★ 2016 Xi et al. / Saito et al.（多机构独立研究）
  实验：面内磁场下 MoS₂/NbSe₂ 等体系的上临界场测量
  结果：面内 Hc₂ 远超 Pauli 极限（增强 2-6 倍）
  解释：Ising SOC 保护 Cooper 对，面内磁场无法有效翻转自旋
  → 提出"Ising 超导体"（Ising superconductor）概念
  [Xi et al. 2016, Nat Phys 12, 139；Saito et al. 2016，来源部分待核查]

★★ 2016–2018 Ising SC 实验深化
  WS₂ 门控 SC 中 Ising 超导更明显（W 比 Mo 原子量大，SOC 更强）
  多组测量 Hc₂ 超出 Pauli 极限：NbSe₂、MoS₂、WS₂ 体系 [来源待验证]

★★ 2018 Li et al. / 相关 WS₂/WSe₂ 研究
  WS₂ 门控 SC Tc ~ 4-5K，Hc₂ 显著超出 Pauli 极限 [来源待验证]
  WSe₂ p 型门控 SC，Tc ~ 几K [来源待验证]

★ 2019–2021 TaS₂ / TaSe₂ 深化研究
  1T-TaS₂：门控抑制 CDW → 出现超导，探索 Mott-SC 转变 [来源待验证]
  多组研究 TMD SC 的 CDW 竞争序 [来源待验证]

★ 2020+ 双层、异质结 TMD 超导
  堆叠 TMD 异质结（例如 WS₂/WSe₂）中的超导和磁性研究 [来源待验证]
  与魔角石墨烯（MATBG）研究的交叉（但 MATBG 属于 D11/B13，不属于 D13）
```

---

## 3. 主要体系详析

### 3.1 MoS₂ 门控超导（D11 的物理补充）

**[基本事实参见 D11；本节展开超导物理细节]**

```
MoS₂ 门控超导的物理细节（[D11 已覆盖基本实验事实]）：

  基本参数：
    Tc ≈ 10.8K（离子液体门控）@ n₂D ~ 10¹⁴ cm⁻² [Ye 2012, Science 338, 1193]（确定）
    超导 dome 形状：n₂D 增加 → Tc 先升后降（经典 BCS dome 行为）[来源待验证]

  Hc₂ 各向异性（D13 核心观测）：[观察]
    面内 Hc₂ >> 面外 Hc₂（各向异性超过 10:1）[来源待验证]
    面内 Hc₂ 超过 Pauli 极限（μ₀Hc₂∥ >> μ₀B_P）[来源待验证]
    → Ising SOC 保护（见第 5 节详细分析）
    面外 Hc₂ 由轨道效应（Orbital depairing）决定，较小

  多层 vs 单层的 Tc 差异：[观察，来源待验证]
    单层 MoS₂：较强 Ising SOC（无反演对称），Ising SC 效应最明显
    多层（4-6 层）：反演对称性逐渐恢复，Ising SOC 减弱，Hc₂/H_Pauli 比值减小
    体材：有反演对称 → 无 Ising SOC → 标准 Hc₂
    → 层数是调控 Ising SC 强度的有效手段

  配对机制（[猜想，当前共识但未严格确认]）：
    MoS₂ 门控 SC 被认为是 BCS-type（声子介导）s-wave 超导（C1 参见）
    Ising SOC 不改变配对对称性（仍是 s-wave），但改变 H 对 SC 的影响
    → 面内 H 场 → Zeeman 分裂，但 Ising SOC 锁定自旋 → Cooper 对受保护 [猜想]
```

### 3.2 单层 NbSe₂（本征 2D 超导与 CDW 竞争）

**[Xi 2016 Nat Phys 数据确定；CDW 机制为 [猜想]]**

```
NbSe₂：TMD 中最重要的本征超导体（不需要门控！）

  体材 NbSe₂（参考基准）[来源待验证，~广泛引用值]：
    Tc（体材）= 7.2K（BCS-type SC）
    T_CDW（体材）= 33K（CDW 转变温度）
    SC 和 CDW 在体材共存（33K > T > 7.2K：CDW 相；T < 7.2K：CDW + SC 共存）
    有反演对称（体材 → 无 Ising SOC）

  单层 NbSe₂ 的维度效应（[Xi 2016, Nat Phys 12, 139]，确定）：
    Tc（单层）≈ 3K（BKT 相变，I-V 曲线 α=3）[确定]
    T_CDW（单层）≈ 145K（CDW 大幅增强！从 33K 升至 145K）[确定]
    
    关键结论（[定理层级 — 实验确认，解释为 [猜想]）：
      ★ 单层中：CDW 增强，SC 减弱！
    
    为什么 CDW 增强？[猜想]
      维度降低 → 费米面嵌套（Fermi surface nesting）增强
      2D 中电子-电子关联更强（库伦相互作用的低维增强）
      CDW 涨落在 2D 中更强（Peierls 不稳定性增强）
    
    为什么 SC 减弱？[猜想，多种机制]
      (a) CDW 开口能隙 → 减少费米面密度态 N(EF) → 弱化 BCS SC
      (b) 2D 中量子相位涨落（BKT 机制）：即使振幅有限，相位涨落也会降低 Tc
      (c) 不是"2D 弱化 SC"的简单说法（⚠️ 见第 8 节反谄媚）

  Ising SOC（单层 NbSe₂ 特有）[定理，来自对称性分析]：
    单层：无反演对称（体材有）→ Ising SOC 出现
    效果：面内 Hc₂ 超过 Pauli 极限 [来源待验证，待核查具体数字]
    与 MoS₂ 的对比：NbSe₂ 是本征 SC，MoS₂ 是门控 SC；Ising SOC 物理相同

  BKT 相变的直接观测（[Xi 2016, Nat Phys 12, 139]，确定）：
    实验：单层 NbSe₂ 的四端电输运测量
    结果：I-V 曲线满足 V ∝ I^α(T)
    T_BKT 处：α = 3（精确满足 BKT 预测）
    T << T_BKT：V → 0（超导）
    T > T_BKT：α = 1（欧姆，正常态）
    → 这是最干净的 2D 超导 BKT 相变实验证据之一
```

### 3.3 TaS₂ / TaSe₂（Mott 绝缘体 + CDW + SC 三者竞争）

**[基本实验事实部分已有报道；机制为 [猜想]]**

```
钽基 TMD：最复杂的竞争序体系

  1T-TaS₂（1T 相，八面体配位）：[来源待验证]
    常压低温态：星状 CDW（commensurate CDW，CCDW）+ Mott 绝缘体
    机制：CDW 形成后，每个 Star-of-David 簇剩余 1 个电子 → Mott 绝缘（强关联）
    门控实验：施加门控（离子液体或固态）→ 抑制 CDW → 出现超导
    Tc（门控）≈ 2-3K [来源待验证]
    研究价值：Mott + CDW + SC 三者竞争的最干净 2D 体系

  2H-TaS₂（2H 相，三棱柱配位）：[来源待验证]
    Tc（常压）≈ 0.8K（体材）
    T_CDW ≈ 75K（CDW 和 SC 竞争）
    门控可提高 Tc：Tc ~ 2-3K（门控后）[来源待验证]

  TaSe₂（单层）：[来源待验证]
    Tc（门控）~ 2K
    CDW 转变温度较高

  与有机超导体（D10）的类比：
    D10（有机 SC，κ-(ET) 系列）也是 Mott + SC 竞争
    但机制不同：D10 是分子晶体，D13 是 2D TMD 无机材料
    相同点：压力/掺杂抑制 Mott 态 → SC 出现（同属"Mott 附近的超导"）[猜想]

  核心物理问题（[猜想]）：
    SC 在 Mott 态附近出现 → 非常规超导的可能性？
    CDW 驱动的配对 vs 声子驱动的配对？
    与铜氧化物（D2）的低载流子密度超导的类比是否成立？[猜想]
```

### 3.4 WS₂ 和 WSe₂（更强 SOC 的 W 基 TMD）

**[[观察]；实验数据 [来源待验证]]**

```
W 基 TMD：更强 Ising SOC 的 Ising 超导体

  为什么 W 比 Mo SOC 更强？[定理，原子物理]
    SOC 强度 λ_SOC ~ Z⁴（Z = 原子序数）
    W（Z=74）>> Mo（Z=42）→ W 基 TMD 的 Ising SOC 更强
    直接后果：面内 Hc₂/H_Pauli 比值在 W 基 TMD 中更大 [观察]

  WS₂（n 型 TMD）：[来源待验证]
    门控超导（离子液体）Tc ~ 4-5K
    面内 Hc₂ 超过 Pauli 极限（违反倍数比 MoS₂ 更显著）
    Ising SOC 强度 λ_I（WS₂）> λ_I（MoS₂）[来源待验证]
    配对对称性：s-wave 为主（[猜想，类比 MoS₂]）

  WSe₂（p 型 TMD，价带超导）：[来源待验证]
    p 型门控（空穴）→ 价带超导
    Tc ~ 1-3K（实验报道不多）
    价带具有更强 SOC 分裂（λ_v >> λ_c，价带分裂比导带大）
    → Ising SC 效应可能更强 [猜想]

  研究意义：
    WS₂ / WSe₂ 提供了 Ising SOC 可调的体系（W vs Mo vs 合金化）
    是研究 Ising SOC 强度 → Hc₂ 增强关系的理想平台 [观察]
```

### 3.5 MoTe₂（拓扑相变附近的超导）

**[实验事实部分确定；TSC 候选为 [猜想]]**

```
MoTe₂：拓扑相变与超导的交叉

  相图（温度 / 压力 / 相）：[来源待验证]
    室温 Td 相（orthorhombic）：Weyl 半金属候选（拓扑非平凡） [来源待验证]
    1T' 相（monoclinic）：拓扑半金属（量子自旋霍尔绝缘体候选）
    超导：Tc ≈ 0.1K（Td 相常压）到 ~ 4K（压力下）[来源待验证]

  为什么 MoTe₂ 有趣？[猜想]
    Weyl 半金属（B13 关联）+ 超导 → 拓扑超导体（D12 交叉）[猜想]
    拓扑相变（Weyl → 普通半金属）附近：超导增强可能？[猜想]
    → 拓扑量子相变 + SC = 非平凡的多体物理

  实验现状 [来源待验证]：
    压力下 Tc 增强（达 ~4K）
    1T'-MoTe₂：Tc ~ 0.1-0.3K
    拓扑性质 + SC 同时存在 → TSC 候选 [猜想，D12 交叉]
    但：Tc 极低，实验测量困难；TSC 证据缺乏 [猜想]

  与 D12（拓扑 SC）的关联：
    MoTe₂ 比 D12 中的 FTS/纳米线证据更弱，Tc 更低
    属于 D13 和 D12 的模糊地带
    当前研究聚焦于相图表征，TSC 具体证据仍在积累 [来源待验证]
```

---

## 4. Ising 超导物理（核心章节）

**[Ising SOC 的哈密顿量和 Pauli 极限为 [定理]；实验观察为 [观察]；配对对称性为 [猜想]]**

```
Ising 超导体（Ising Superconductor）的完整物理框架：

  标准 BCS Cooper 对的磁场破坏（[定理]）：
    (a) 轨道效应（Orbital depairing）：磁场 → 洛伦兹力 → 破坏 Cooper 对轨道
         特征磁场：Hc₂^{orb} ~ Φ₀/ξ²（相干长度 ξ 决定）
    (b) Pauli 顺磁效应（Pauli depairing）：Zeeman 分裂 → 自旋翻转 → 破坏 singlet
         Pauli 极限（[定理，Clogston-Chandrasekhar 极限]）：
         LaTeX: \mu_0 H_P = \frac{\Delta_0}{\sqrt{2} \mu_B} \approx 1.86 T_c \text{ [Tesla/K]}
         ASCII: mu_0 * H_P = Delta_0 / (sqrt(2) * mu_B) ≈ 1.86 * Tc [T/K]
         对于 Tc = 10K：H_P ≈ 18.6T

  Ising SOC 如何保护 Cooper 对（[定理]）：
    
    Ising SOC 哈密顿量（H 相 TMD 单层）：
    LaTeX: H_{Ising} = \lambda_I \tau_z \sigma_z
    ASCII: H_Ising = lambda_I * tau_z * sigma_z
    
    效果：
      K 谷（tau_z = +1）：↑ 自旋能量被 lambda_I 修正 → 自旋锁定在 +z 方向
      K' 谷（tau_z = -1）：↓ 自旋被锁定在 -z 方向
    
    Cooper 对的谷结构（[定理]）：
      Ising SC 中的 Cooper 对：(K↑, K'↓) 配对
      （不是 (k↑, -k↓) 的普通动量空间配对，而是谷-自旋结构）
    
    面内磁场 H∥ 的效应（[定理 + 猜想混合]）：
      面内 Zeeman 场：H_{Zeeman} = g* μ_B H∥ σ_x（x 方向，面内）
      问题：σ_x 试图翻转 σ_z 锁定的自旋
      Ising SOC 提供抵抗：只要 lambda_I >> g* μ_B H∥，自旋锁定维持
      → 面内 Hc₂ 大幅超过 Pauli 极限！[定理]
    
    理论极限（无轨道效应时）：[定理]
      H∥_{c2} → ∞（完美 Ising SOC，理论极限）
      实际上：轨道效应（即使面内也有有限 L/ξ₀ 修正）限制真实 Hc₂
      实验观察：面内 H_{c2} >> H_Pauli（超出 2-10 倍）[观察]

  实验证据（[观察]）：
    NbSe₂ 单层：H∥c₂ 超出 H_Pauli [Xi 2016, Nat Phys 12, 139]（确定，具体比值待验证）
    MoS₂：H∥c₂/H_Pauli > 2 [来源待验证]
    WS₂：H∥c₂/H_Pauli 超出更明显（更强 SOC）[来源待验证]

  ⚠️ 关键反谄媚：Ising SC ≠ triplet 配对！[定理]
    常见误区：Pauli 极限违反 → triplet（奇次）配对？
    正确分析：
      Pauli 极限违反有两种机制：
        (a) 奇次配对（triplet）：自旋非零 → Zeeman 不破坏对称
        (b) SOC 保护的 singlet：Ising SOC 锁定自旋 → 面内 Zeeman 失效
      Ising SC 是机制 (b)！配对仍然是 singlet（s-wave）[猜想，MoS₂/NbSe₂ 的当前共识]
    → D11 已强调，D13 完整展开此澄清
```

---

## 5. 2D 超导中的 CDW 竞争序

**[CDW 竞争是 [观察]；微观机制为 [猜想]]**

```
2D 中 CDW 与 SC 的竞争：

  为什么 2D 体系中 CDW 更强？[定理 + 猜想混合]
    (a) Fermi 面嵌套增强 [猜想]：低维 → 费米面平坦部分增多 → 嵌套更完美
    (b) 相关函数的低维增强 [定理，Mermin-Wagner 定理的推论]：
        2D 中长程序在有限温被热涨落抑制，但短程 CDW 涨落更强
    (c) 电子-晶格耦合效率：2D 材料的声子结构不同于体材 [猜想]

  NbSe₂ 的维度效应（最干净的例子）：
    体材：T_CDW = 33K，Tc = 7.2K → SC 赢，CDW 弱
    单层：T_CDW = 145K，Tc = 3K → CDW 赢，SC 被压制
    CDW/SC 能量尺度反转！[Xi 2016, Nat Phys 12, 139]（确定）

  CDW 如何抑制 SC？[猜想，标准图像]
    CDW 在费米面开口部分能隙（Peierls 能隙）→ 减少 N(EF)
    LaTeX: T_c \sim \omega_D \exp\left(-\frac{1}{N(E_F) V_{e-ph}}\right)
    ASCII: Tc ~ omega_D * exp(-1 / (N(EF) * V_e-ph))
    N(EF) 减小 → Tc 下降（指数敏感！）

  CDW 是否可以辅助 SC？[猜想，争议]
    CDW 涨落（B6）提供额外的电子-电子相互作用通道
    → 可能在部分能带区域增强配对 [猜想]
    反驳：CDW 的主要效应是减少 N(EF)，净效果是抑制 SC [猜想]
    → 目前无决定性实验区分

  TaS₂：门控抑制 CDW → SC 出现：[观察，来源待验证]
    门控增加载流子密度 → 改变 CDW 嵌套条件 → CDW 弱化
    同时：SC 出现（类似于铜氧化物掺杂相图中 Mott 被抑制后出现 SC）[类比，猜想]

  与 B6（CDW 节点）的关联：
    B6 提供 CDW 的理论框架（Peierls 不稳定性、Fröhlich Hamiltonian 等）
    D13 是 B6 在 TMD 单层中的具体实现案例
    NbSe₂ 和 TaS₂ 是 B6 + D13 双节点的关键材料
```

---

## 6. 关键定量数据

**[严格区分来源确定性；[来源待验证] 意味着数值可能有偏差]**

```
MoS₂（门控 SC）：
  Tc = 10.8K @ n₂D ~ 10¹⁴ cm⁻² [Ye et al. 2012, Science 338, 1193]（确定）
  SC dome：Tc 随 n₂D 先升后降（dome 形状）[来源待验证]
  面内 Hc₂ / H_Pauli > 2（Ising SC）[来源待验证]

NbSe₂（单层）：
  Tc（BKT）≈ 3K [Xi et al. 2016, Nature Physics 12, 139]（确定）
  T_CDW（单层）= 145K [Xi et al. 2016, Nature Physics 12, 139]（确定）
  BKT 判据：I-V 曲线 α = 3 在 T_BKT [Xi 2016]（确定）
  Ising SC：面内 Hc₂ 超出 Pauli 极限 [Xi 2016，具体倍数待核查]

NbSe₂（体材）：
  Tc = 7.2K [来源待验证，广泛引用]
  T_CDW = 33K [来源待验证，广泛引用]

WS₂（门控 SC）：
  Tc ~ 4-5K（离子液体门控）[来源待验证]
  Hc₂/H_Pauli：比 MoS₂ 更大（W SOC 更强）[来源待验证]

WSe₂（p 型门控 SC）：
  Tc ~ 1-3K（报道较少）[来源待验证]

TaS₂（1T，门控 SC）：
  Tc ~ 2-3K（门控诱导）[来源待验证]

TaSe₂（单层，门控）：
  Tc ~ 2K [来源待验证]

MoTe₂（压力 SC）：
  Tc（常压）≈ 0.1K（Td 相）[来源待验证]
  Tc（压力下）~ 4K [来源待验证]

Pauli 极限（标准值，[定理]）：
  μ₀H_P ≈ 1.86 × Tc [Tesla/K]
  MoS₂（Tc=10.8K）：H_P ≈ 20T（理论值）
  NbSe₂ 单层（Tc=3K）：H_P ≈ 5.6T（理论值）

λ_I（Ising SOC 强度，理论计算）[来源待验证]：
  MoS₂（导带）：λ_I ~ 3-5 meV
  WS₂（导带）：λ_I ~ 20-30 meV（更强！）
  MoS₂（价带）：λ_I ~ 70-80 meV（价带比导带大得多）
  → 价带 WSe₂/WS₂ 的 Ising SC 效应预计最强 [猜想]
```

---

## 7. 关键反谄媚

**[纠正 D13 领域的常见误区；防止不当类比和过度声明]**

```
反谄媚 1：NbSe₂ 单层 Tc 降低 ≠ "2D 弱化超导"的简单说法

  ✅ 事实：NbSe₂ 单层 Tc = 3K < 体材 7.2K（降低）
  ✅ 正确解释（多因素）：
    (a) CDW 大幅增强（145K vs 33K）→ N(EF) 减少 → Tc 下降 [主要因素，猜想]
    (b) BKT 机制：2D 中相位涨落 → T_BKT < T_c^{mean-field} [定理，起作用]
    (c) 不是"2D 弱化 SC"——NbSe₂ 的 2D 量子涨落效应是次要的
  ❌ 错误说法："2D 限制天然弱化超导"
  ✅ 反例：FeSe/STO 单层 Tc ~ 60-70K（界面增强，D11）

反谄媚 2：Ising SOC 保护的面内 Hc₂ 增强 ≠ triplet 配对

  ✅ 事实：面内 Hc₂ >> H_Pauli 在 MoS₂/NbSe₂/WS₂ 中观测到
  ❌ 错误推论：Pauli 极限违反 → triplet（奇次）配对 → 非常规 SC
  ✅ 正确解释：Ising SOC（时间反演对称保持，谷-自旋锁定）保护 singlet Cooper 对
              面内磁场无法有效翻转被 λ_I τ_z σ_z 锁定的自旋
              配对仍是 s-wave singlet（C1）[猜想，当前共识]
  ✅ 区分：triplet SC（C5，如 Sr₂RuO₄ 候选）是配对对称性不同；Ising SC 是 SOC 保护 singlet

反谄媚 3：MATBG 魔角石墨烯不属于 D13！

  ✅ MATBG（Magic Angle Twisted Bilayer Graphene）属于：
    B13（平坦带强关联 SC）：平坦带 → Mott 绝缘体 → SC（强关联机制）
    D11（2D/界面）：界面处（层间耦合决定）的超导
  ❌ 错误归类：MATBG → D13（"2D 半导体超导"）
  ✅ 区别：D13 的超导来自半导体 TMD 材料本身，通过门控等诱导；
           MATBG 是强关联平坦带效应，机制完全不同
  ✅ D13 专注"真正的"半导体（MoS₂、NbSe₂ 等），不包括 MATBG

反谄媚 4：D13 的 Tc 低（1-12K）但研究价值极高

  ✅ 事实：TMD SC 的 Tc 在 1-12K 范围，无实用超导价值
  ❌ 错误结论："Tc 太低，研究价值有限"
  ✅ 研究价值（非应用价值）：
    (a) 最干净的 2D 超导实验平台（薄至单层，可门控）
    (b) Ising SOC 物理的理想体系（不混杂三维效应）
    (c) BKT 物理直接实验验证
    (d) CDW+SC 竞争序的可控调控（E3 门控工具）
    (e) 潜在 TSC 候选（MoTe₂ 等）的研究基础

反谄媚 5：D13 与 D11 的重叠处理

  MoS₂ 门控超导同时属于 D11 和 D13：
    D11 已覆盖：基本实验事实（Tc≈10.8K，首次 TMD SC）+ 界面/2D 超导框架
    D13 专注：超导物理细节（Ising SOC、Hc₂ 各向异性、配对对称性、dome 形状）
  处理规则：D13 不重复 D11 的核心叙述，专注 D13 特有的超导物理分析
  边界判定：凡是超导机制 + 材料物理（SOC/CDW/配对）→ D13；
            凡是界面/衬底/近邻效应 → D11

反谄媚 6：[来源待验证] 的比例在 D13 中很高

  ✅ 事实：D13 多个数值和实验结论标注 [来源待验证]
  ✅ 原因：TMD SC 领域发展快，多篇重要论文（2015-2020 年）未经精确核查
  ✅ 正确使用方式：[来源待验证] 的结论可作为研究方向，但不应作为定量预测输入
  ✅ 优先级：Xi 2016 Nat Phys（NbSe₂），Ye 2012 Science（MoS₂）来源已确认，
             其余多数来源需核查
```

---

## 8. 与 Paper A/B 及 MECE 框架的关联

**[框架适用性分析 — 明确适用范围和超出范围]**

```
D13 与 Paper A（多通道 Allen-Dynes Eliashberg 框架）：

  部分适用体系：
    MoS₂ 门控 SC（BCS s-wave，声子介导）：
      Allen-Dynes 框架原则上适用（BCS 型，λ_ep 可定义）
      但：2D 声子谱 + Ising SOC 对 λ_ep 的影响需要修正 [猜想]
      实际困难：门控浓度调控的 2D 电子系统的 λ_ep 难以精确计算
    
  超出框架的体系：
    NbSe₂ 单层（CDW + SC 竞争）：
      CDW 大幅改变费米面，Allen-Dynes 需要 CDW 涨落修正
      标准 Allen-Dynes 输入（正常态声子谱 + N(EF)）在 CDW 体系中不再有效
    
    TaS₂（Mott + CDW + SC）：
      Mott 强关联完全超出声子介导 SC 框架
      → Allen-Dynes 不适用 [定论]
    
    MoTe₂（拓扑 + SC）：
      拓扑机制相关的配对超出 Allen-Dynes 描述范围

  结论：D13 中 BCS-type 体系（MoS₂ 等）可用 Allen-Dynes 作近似估计，
        但 CDW/Mott/拓扑体系均超出框架。Paper A 的主要应用在传统金属和氢化物（D1-D3）。

D13 与 MECE 框架关联图：
  E3（门控）→ D13 的主要调控手段（离子液体 EDLT）
  F8（BKT）→ 所有 D13 体系的 2D 超导相变机制（NbSe₂ 最干净的实验）
  B6（CDW）→ NbSe₂、TaS₂ 中 CDW 竞争序（D13 是 B6 的主要材料节点）
  C1（s-wave）→ MoS₂ 等门控 SC 的配对对称性（s-wave singlet，[猜想]）
  D11（2D/界面）→ D13 的框架关联（共享 2D 物理，但侧重不同）
  D12（TSC 候选）→ MoTe₂ 的拓扑 SC 候选性质（D13 + D12 交叉）
  B13（平坦带）→ MATBG 不属于 D13！（已明确排除）
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026） | 主要障碍 | 相关 MECE |
|------|----------------|---------|-----------|
| **TMD SC 中是否存在 singlet-triplet 混合配对？** | [猜想，开放；当前共识是 singlet] | 配对对称性测量（NMR/比热/穿透深度）极难在 2D 体系进行 | C5, C9 |
| **CDW 增强与 SC 抑制的精确微观机制** | [猜想，开放] | 需要 k 空间分辨的 CDW + SC 联合测量（ARPES + STM） | B6 |
| **MoTe₂ 是否为拓扑超导体候选？** | [猜想，早期阶段] | Tc 极低（0.1K）+ 拓扑证据不足 | D12, B11 |
| **2D 半导体中能否实现 Tc > 20K？** | [猜想，未有报道] | 门控诱导 SC 的 N(EF) 上限 + 2D 声子耦合限制 | C1, E3 |
| **Ising SOC 是否可以完全保护面内 Hc₂（达理论无穷）？** | [猜想；实际有限] | 轨道效应在薄层中仍有贡献，需极低 T 精确测量 | — |
| **价带 WSe₂/WS₂（p 型 Ising SC）的 Hc₂ 行为** | [猜想；价带 SOC 更强，预计更好] | p 型门控效率较低，样品质量控制 | — |
| **TaS₂ 附近的超导：声子介导还是 Mott 涨落介导？** | [猜想，核心争议] | CDW+Mott+SC 三者竞争的理论和实验分析 | B6, D10 |
| **InSe、GaTe 等 p 型 2D 半导体的超导** | [探索阶段，少量报道] | 材料制备困难，门控效率低 | — |

---

## 附录：核心速查（ASCII 格式）

```
=== D13 二维半导体超导体 核心速查 ===

[1] 五大体系总览：
  MoS₂（门控，n 型）：
    Tc = 10.8K @ 10¹⁴ cm⁻² [Ye 2012, Science 338, 1193]（确定）
    机制：BCS s-wave（[猜想]）+ Ising SOC
    特点：首个 TMD SC，超导 dome，Hc₂ > H_Pauli

  NbSe₂（本征，单层）：
    Tc ≈ 3K（BKT）[Xi 2016, Nat Phys 12, 139]（确定）
    T_CDW = 145K（单层！vs 体材 33K）[Xi 2016]（确定）
    特点：最干净的 2D BKT 实验；CDW+SC 竞争

  TaS₂（1T/2H，门控）：
    Tc ~ 2-3K（门控）[来源待验证]
    特点：Mott + CDW + SC 三者竞争；类 Mott SC（类比有机 SC）

  WS₂（门控，n 型）：
    Tc ~ 4-5K [来源待验证]
    特点：W 的更强 SOC → Hc₂ 超出 Pauli 极限更显著

  MoTe₂（拓扑 + SC）：
    Tc ~ 0.1-4K（压力依赖）[来源待验证]
    特点：Weyl 半金属 + SC → TSC 候选（D12 交叉）[猜想]

[2] 核心物理公式：
  Ising SOC 哈密顿量：
    H_Ising = lambda_I * tau_z * sigma_z  [定理]
    效果：K/K' 谷自旋锁定 ±z → 面内 H 场无法翻转 → Hc₂^∥ >> H_Pauli

  Pauli 极限（无 SOC 时）：
    mu_0 * H_P = Delta_0 / (sqrt(2) * mu_B) ≈ 1.86 * Tc [T/K]  [定理]

  BKT 相变判据：
    I-V 曲线：V ~ I^alpha
    alpha -> 3 at T_BKT（超导-正常态边界）  [定理]

[3] 维度效应（NbSe₂ 经典案例）：
  体材：Tc = 7.2K，T_CDW = 33K（SC > CDW）
  单层：Tc = 3K，  T_CDW = 145K（CDW >> SC）
  结论：降维 → CDW 增强 → SC 被压制  [Xi 2016，确定]

[4] 核心反谄媚：
  ⚠️ Ising SC Pauli 极限违反 ≠ triplet 配对（是 SOC 保护的 singlet）
  ⚠️ MATBG 不属于 D13（属于 B13/D11 平坦带强关联）
  ⚠️ NbSe₂ 单层 Tc 降低 ≠ "2D 弱化 SC"（CDW 增强 + BKT 是主因）
  ⚠️ D13 与 D11 有重叠（MoS₂ 门控 SC），D13 聚焦超导物理，D11 聚焦界面机制

[5] 来源可靠性评级：
  ✅ 确定：Ye 2012 Science 338, 1193（MoS₂ Tc=10.8K）
  ✅ 确定：Xi 2016 Nat Phys 12, 139（NbSe₂ 单层 Tc=3K，CDW=145K，BKT）
  ⚠️ 待验证：WS₂/WSe₂/TaS₂ 的定量数据
  ⚠️ 待验证：MoTe₂ 超导的精确 Tc 范围
  ⚠️ 待验证：Lu 2015 Science 350, 1353（多 TMD 门控 SC 研究）

=== D13 与 MECE 关联图 ===
  E3（门控）→ D13 的调控主手段（离子液体 EDLT）
  F8（BKT）→ 2D SC 相变机制（NbSe₂ 单层最干净实验）
  B6（CDW）→ NbSe₂/TaS₂ 竞争序（D13 = B6 的核心材料案例）
  C1（s-wave）→ MoS₂ 等配对对称性（singlet s-wave，猜想）
  D11（2D/界面）→ 共享 2D 物理框架（MoS₂ 门控两节点关联）
  D12（TSC）→ MoTe₂ 拓扑 SC 候选（D13+D12 交叉）
  B13（平坦带）→ 明确排除 MATBG
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**字节大小估计：** ~13.5 KB

**反谄媚审计：**
- ✅ Ising SC ≠ triplet 配对，完整物理解释（第 4 节 + 第 7 节）
- ✅ MATBG 明确排除在 D13 之外（属于 B13/D11）
- ✅ NbSe₂ 单层 Tc 降低的多因素解释（CDW + BKT + 涨落，不是简单"2D 弱化"）
- ✅ D13 与 D11 的边界清楚界定，不重复 D11 的核心内容
- ✅ 大量 [来源待验证] 标注（诚实面对数据不确定性）
- ✅ 两个确定来源（Ye 2012、Xi 2016）与待验证来源清楚区分
- ✅ 配对机制（s-wave）标注 [猜想] 而非定论
- ✅ MoTe₂ 的 TSC 候选性质标注 [猜想]，与 D12 交叉明确说明
- ✅ CDW 辅助配对标注 [猜想]，承认争议存在

**D 部分状态：** D1 ✅ → … → D12 ✅ → **D13 ✅（当前）**
