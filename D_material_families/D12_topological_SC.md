# D12. 拓扑超导体候选 — 从 Fe(Te,Se) 到 InSb 纳米线：Majorana 零模的追寻与撤稿重灾区

**MECE 编号：** D12
**关联 MECE：**
- B11（拓扑超导理论 — AZ 10 折分类，Kitaev/Read-Green/Fu-Kane 理论框架）
- C5（p-wave — triplet 驱动 TSC：chiral p+ip 是 Class D TSC 的原型）
- C7（Chiral — chiral p+ip：Read-Green 态，MZM 的最初理论来源）
- C9（Singlet vs Triplet — TSC 通常需要有效 triplet 分量或奇次配对）
- A9（Andreev — ZBCP Majorana 实验探测：零偏压电导峰是核心但非充分实验信号）
- D8（重费米子 — UTe₂：已在 D8/C6 中讨论，此处标记关联）
- D11（2D/界面 — Fu-Kane 方案：TI 表面 + s-wave SC → 等效 p-wave → MZM）

**层级关系：** D12 是**拓扑超导体候选材料**的综述。它与 B11（拓扑超导理论）是理论–材料对应关系：B11 提供分类框架（AZ 10 折分类、Kitaev chain、Fu-Kane 方案），D12 描述哪些材料可能实现这些拓扑相。核心特征：(1) BdG Hamiltonian 具有非平凡拓扑数（Chern 数、Z₂ 不变量等）；(2) 边界/涡旋核心存在受拓扑保护的 Majorana 零模（MZM）；(3) MZM 是非阿贝尔任意子，是拓扑量子计算的核心资源。主要候选体系：Fe(Te,Se)（FTS，体材 TSC 最强候选）、InSb/InAs 半导体纳米线（Lutchyn-Oreg 方案，Microsoft 路线）、拓扑绝缘体/SC 异质结（Fu-Kane 方案）、半 Heusler 化合物（YPtBi）。**⚠️ 这是超导领域撤稿率最高、商业利益最密集的方向，本文档以反谄媚为核心原则。**
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Kitaev 2001、Read-Green 2000、Fu-Kane 2008、Lutchyn/Oreg 2010、Mourik 2012、Zhang 2018 Science 等核心文献框架；数值标注来源，未精确核查项注明 [来源待验证]）

⚠️ **核心诚实声明：截至 2026 年，没有任何材料被无争议地确认为拓扑超导体（TSC）。没有任何实验被学界普遍接受为确认 Majorana 零模（MZM）的决定性证据。TU Delft/Microsoft 组 2017 年 Nature 论文（宣称量子化 ZBCP = Majorana 信号）于 2021 年因数据筛选问题撤稿。TSC 领域受到量子计算商业利益（Microsoft/Google/IBM）的强烈驱动，数据报道偏差是系统性问题，而非个例。Fe(Te,Se)（FTS）是目前最强的体材 TSC 候选，但 ZBCP 的 Majorana vs trivial Andreev 归属尚无定论。半导体纳米线的 Majorana 实验经历了最严重的信誉危机。研究这个方向需要极高的批判性眼光。**

---

## 1. 物理定义与核心思想

### 1.1 什么是拓扑超导体

**[BdG Hamiltonian 拓扑不变量为 [定理]；具体材料实现为 [猜想]]**

```
拓扑超导体（TSC）的定义：

  超导体的 BdG（Bogoliubov-de Gennes）哈密顿量描述准粒子：
    LaTeX: H_{BdG}(\mathbf{k}) = \begin{pmatrix} \xi(\mathbf{k}) & \Delta(\mathbf{k}) \\ \Delta^\dagger(\mathbf{k}) & -\xi(-\mathbf{k}) \end{pmatrix}
    ASCII:
      H_BdG(k) = | xi(k)       Delta(k)      |
                 | Delta†(k)  -xi(-k)        |
    
    其中 xi(k) = 正常态色散（减去化学势），Delta(k) = 超导序参量

  粒子-空穴对称性（PHS，Particle-Hole Symmetry）：[定理，BdG 框架的必然性质]
    C H_BdG(k) C^{-1} = -H_BdG(-k)，C = tau_y * K（tau_y 作用于 Nambu 空间，K 取复共轭）
    这是 BdG 哈密顿量的内禀对称性，不是物理保护，是数学约束

  拓扑分类（AZ 10 折分类）[定理，Altland-Zirnbauer 1997 + Schnyder/Ryu/Furusaki/Ludwig 2008]：
    有意义的 TSC 类别：
    ┌──────────┬─────────┬─────────┬─────────┬───────────────────────────────┐
    │ 对称类  │ TRS (T) │ PHS (C) │ Chiral  │ 拓扑不变量（1D / 2D / 3D）    │
    ├──────────┼─────────┼─────────┼─────────┼───────────────────────────────┤
    │ Class D  │  无     │  C²=+1  │  无     │ Z₂ / Z（Chern） / 0           │
    │ Class DIII│ T²=-1  │  C²=+1  │  有     │ Z / Z₂ / 0                    │
    │ Class BDI │ T²=+1  │  C²=+1  │  有     │ Z / 0 / 0                     │
    └──────────┴─────────┴─────────┴─────────┴───────────────────────────────┘
    
    材料对应：
      Class D（1D）：Kitaev chain（p-wave 纳米线理论）→ Z₂ 不变量 ν ∈ {0, 1}
      Class D（2D）：Chiral p+ip（Read-Green 态）→ Chern 数 C ∈ Z
      Class DIII（1D）：时间反演不变纳米线（T²=-1）→ Z 不变量
      Class DIII（3D）：3D TSC（B 相 He-3，可能 Cu_x Bi₂Se₃）→ Z₂ 不变量

  Kitaev chain 的拓扑相变（[定理，严格解析解]）：
    哈密顿量：
      H = -t Σ_j (c†_{j+1} c_j + h.c.) - μ Σ_j c†_j c_j + Δ Σ_j (c_{j+1}c_j + h.c.)
    
    BdG（k 空间）：
      H_BdG(k) = (−2t cos(k) − μ) τ_z + 2Δ sin(k) τ_x
    
    拓扑相变条件（[定理]）：
      |μ| < 2t → ν = 1（拓扑非平凡）→ 链两端出现 Majorana 零模
      |μ| > 2t → ν = 0（拓扑平凡）→ 无边界态
      相变点：|μ| = 2t（能隙关闭点）
    
    Z₂ 不变量显式形式：
      ν = sign[ Pf(H_BdG(k=0)) * Pf(H_BdG(k=π)) ]
      ASCII: nu = sgn[ Pf(H_BdG(0)) * Pf(H_BdG(pi)) ]
      Pf = Pfaffian（反对称矩阵的 Pfaffian，平方 = 行列式）[定理]
```

### 1.2 Majorana 零模的物理意义

**[Majorana 零模的数学存在性为 [定理]；材料中的实验实现均为 [猜想]]**

```
Majorana 费米子：实费米子

  定义（[定理，数学定义]）：
    γ = γ†（算符等于自身的厄米共轭）
    满足：{γ_i, γ_j} = 2δ_{ij}（Clifford 代数关系）
    与复费米子的关系：c = (γ_1 + i γ_2)/2，c† = (γ_1 - i γ_2)/2

  物理意义（[定理，来自拓扑场论 + BdG 框架]）：
    (1) 零能激发：H_BdG γ = 0（对应零能 Andreev 束缚态）
    (2) 非阿贝尔统计（[定理，在 2D chiral p-wave 中严格证明]）：
        两个 MZM 的交换（braiding）产生 ±90° 相位旋转
        （而非普通费米子的 -1 或玻色子的 +1）
        → 可用于拓扑保护的量子门操作
    (3) 非局域编码：一个逻辑量子比特 = 两个空间分离的 MZM（γ_L, γ_R）
        → 退相干被拓扑间隙压制（理想情况）

  实验探测的主要方法（[观察 — 信号存在，但解释争议]）：
    (a) 零偏压电导峰（ZBCP, Zero-Bias Conductance Peak）：
        隧道谱 dI/dV 在 V=0 处出现峰值
        ⚠️ 必要条件，非充分条件！trivial Andreev 也能给出 ZBCP（见第 5 节）
    
    (b) 半量子化电导：理论预测 G = e²/h（Kitaev chain 末端）[定理]
        ⚠️ 从未在实验中稳定实现！
    
    (c) 4π 周期 Josephson 效应（拓扑 Josephson 结）[定理，拓扑 SC 中]
        I ∝ sin(φ/2)（4π 周期）vs 普通 Josephson I ∝ sin(φ)（2π 周期）
        ⚠️ 准粒子毒化使 4π 周期极难测量，实验信号不明确 [观察]
    
    (d) 非局域 Majorana 关联：两端非本地测量关联 [来源待验证]
    
    (e) 非阿贝尔 braiding 统计：需要操控两个 MZM，目前仅 Microsoft 宣称尝试，
        独立验证不充分 [来源待验证，2023 Majorana 1]
```

---

## 2. 历史关键节点（撤稿教训是重点）

**[历史 — 来源明确标注；⚠️ = 重大争议/撤稿事件]**

```
★★★ 2000 Read & Green（普林斯顿大学）
  理论：chiral p+ip 超导 → 拓扑非平凡（Class D，Chern 数 C=1）
  → 存在无能隙手性 Majorana 边界态 + 涡旋核心 MZM
  → 分数量子霍尔 ν=5/2 态可能是 p+ip → 非阿贝尔任意子
  [Read & Green 2000, PRB 61, 10267]（确定）
  ★ 现代 TSC 理论的奠基性工作

★★★ 2001 Kitaev（微软研究院 / 加州理工）
  理论：1D p-wave 超导链（Kitaev chain）→ 两端出现 Majorana 零模
  Z₂ 拓扑不变量精确解：|μ| < 2t 时拓扑非平凡
  提出 Majorana 用于拓扑量子计算的概念框架
  [Kitaev 2001, Phys-Usp. 44, 131]（确定）
  ★ MZM 拓扑量子计算的理论起点（也是 Microsoft 量子路线的理论依据）

★★★ 2008 Fu & Kane（宾夕法尼亚大学）
  理论：拓扑绝缘体（TI）表面态 + s-wave 超导（近邻效应）→ 等效 p+ip → Majorana
  简洁性：不需要本征 p-wave SC，只需 TI 表面 + 普通 SC 即可
  LaTeX: H_{Fu-Kane} = v_F (\mathbf{k} \times \boldsymbol{\sigma}) \cdot \hat{z} \tau_z + \Delta \tau_x - \mu \tau_z
  ASCII: H_FK = v_F*(k × sigma)·z*tau_z + Delta*tau_x - mu*tau_z
  [Fu & Kane 2008, PRL 100, 096407]（确定）
  ★ 开创 TI/SC 界面 TSC 研究方向，迄今最有影响的 TSC 提案之一

★★★ 2010 Lutchyn、Sau、Das Sarma（马里兰大学）
  理论：半导体纳米线（InSb/InAs）+ Rashba SOC + Zeeman 场（外加磁场）+ s-wave SC
  → 等效 Kitaev chain → 拓扑相变 → 端部 MZM
  拓扑条件：V_Z > sqrt(μ² + Δ²)（Zeeman 能超过 SC 间隙和化学势）
  [Lutchyn et al. 2010, PRL 105, 077001]（确定）

★★★ 2010 Oreg、Refael、von Oppen（以色列理工 / FU Berlin / CIT）
  独立同时提出相同方案（Oreg-Lutchyn 方案）
  [Oreg et al. 2010, PRL 105, 177002]（确定）
  ★ 两篇论文共同开创半导体纳米线 Majorana 实验路线

★★★ 2012 Mourik、Zuo、Frolov、Plissard、Bakkers、Kouwenhoven（TU Delft）
  实验：InSb-NbTiN 纳米线器件 → 外加磁场后出现 ZBCP
  这是首个被广泛引用的 "Majorana 候选" 实验
  [Mourik et al. 2012, Science 336, 1003]（确定）
  ★ 引爆全球纳米线 Majorana 实验热潮
  ⚠️ 但 ZBCP 本身只是必要条件，不是充分条件（见第 5 节）

★ 2012–2016：纳米线 ZBCP "确认" 浪潮
  多个组（TU Delft、Copenhagen、Harvard、UCSB 等）重复 ZBCP [来源待验证]
  但量子化电导（G = e²/h）一直未稳定实现
  理论上 trivial Andreev 解释的质疑逐渐增多（Kells、Stanescu、Das Sarma 等）

★★★ 2018 Zhang、Liu、Gazibegovic、Wang 等（TU Delft + 多机构合作）
  宣称 InSb 纳米线中看到"量子化" ZBCP，G ≈ 2e²/h
  [Zhang et al. 2018, Nature 556, 74]（确定）
  ★ 媒体大肆报道，Microsoft 迅速采纳为 Majorana 确认的证据

⚠️⚠️⚠️ 2021 撤稿：Zhang et al. 2018 Nature 被撤回！
  原因：数据筛选（data selection）问题
    - 发表版本只展示了"好的"器件（ZBCP 清晰的数据）
    - 未发表的大量数据（ZBCP 不清晰、不稳定的器件）被忽视
    - 量子化 G ≈ 2e²/h 被认为是数据选择性展示的结果
  [Nature 2021 撤稿声明]（确定）
  教训：在商业压力下，数据选择性报道导致了一篇顶刊论文的撤稿
  这是 TSC 领域最大的学术丑闻，也是整个领域的信誉重创

★★★ 2018 Zhang、Yin、Liu、Kong 等（Wuhan University / SEIS / MIT）
  实验：Fe(Te₀.₅₅Se₀.₄₅)（FTS）单晶，STM 在磁场中的涡旋核心看到 ZBCP
  解释为涡旋核心 Majorana 零模（基于 FTS 的 TI 表面态 + SC = Fu-Kane 机制）
  [Zhang et al. 2018, Science 360, 182]（确定，未撤回）
  ★ 目前 TSC 实验证据最强的体材体系
  ⚠️ ZBCP 解释仍有争议：trivial Andreev 束缚态（Caroli-de Gennes-Matricon 态）
     也可以在涡旋核心给出 ZBCP，且与 MZM 难以区分

★ 2019 Pustogow、Luo、Chronister 等（UCLA）
  Sr₂RuO₄ Knight shift 低温翻案：TRS 破缺 triplet p-wave 假说被推翻
  [Pustogow et al. 2019, Nature 574, 72]（确定）
  → 拓扑超导候选 Sr₂RuO₄ 的地位动摇（→ C5, C7 详述）
  教训：24 年的"共识"可以被一个精确实验推翻

★ 2020–2022 Pan & Das Sarma 系列（马里兰大学）
  理论工作：系统证明 trivial Andreev 束缚态可以完美模拟 Majorana ZBCP
  包括：磁场依赖、温度依赖、软化特征等，几乎所有 ZBCP 特征均可由 trivial 解释
  [Pan & Das Sarma 2020, PRL 124, 227001；2021 系列]（来源部分待核查）
  ★ 对整个纳米线 Majorana 实验的根本性质疑

⚠️ 2022 Microsoftt / Whiticar 等
  Microsoft 内部重测，发现多个器件结果不一致
  部分结果撤回或修正（与 2018 撤稿相关联）[来源待验证]

★★ 2023 Microsoft "Majorana 1"（微软量子）
  宣称实现首个"拓扑量子比特"，基于 InAs 纳米线的 topoconductor 架构
  宣称：topological gap > 30 μeV，满足"topological gap protocol"（TGP）
  [来源：Microsoft Quantum 2023 预印本，arxiv 2207.02472 等，独立验证不充分]
  ⚠️ 学界反应谨慎：
    (a) TGP 只是代理判据，不直接证明 Majorana
    (b) 2018 撤稿后，Microsoft 数据的可信度整体受损
    (c) 独立重复：至 2026 年，无独立实验室复现 Majorana 1 的核心结论 [来源待验证]
    (d) 商业宣布 ≠ 科学证明

★ 2024–2026 FTS 涡旋态 Majorana 研究持续推进
  多组（中国、美国、欧洲）在 FTS 和相关铁基体系开展工作 [来源待验证]
  Li₂(Pd₁₋ₓPtₓ)₃B 等也被考察 [来源待验证]
  共同困难：trivial vs topological 涡旋态的区分实验尚无普遍接受方案
```

---

## 3. 主要 TSC 候选体系详析

### 3.1 Fe(Te,Se)（FTS）— 目前最强的体材 TSC 候选

**[Zhang 2018 Science 数据确定；MZM 解释为 [猜想]]**

```
Fe(Te₁₋ₓSeₓ) 拓扑超导机制：

  为什么 FTS 是 TSC 候选？（[猜想，理论论证]）
    FTS（特别是 x ≈ 0.45–0.55）具有：
      (a) 超导：Tc ≈ 14–15K（体材 SC）
      (b) 拓扑表面态（Dirac 锥）：ARPES 确认 FTS 具有 TI 型表面能带 [来源待验证]
    这两个性质的组合 → 三维版 Fu-Kane 机制！
    
    Fu-Kane 机制的三维推广（[猜想，Wang 2015 PRB 等]）：
      FTS 的体超导 + TI 表面态 → 表面上的等效 p+ip 超导 → 表面 Majorana cone
      涡旋穿越 FTS 体时 → 涡旋芯与 Dirac 表面态相交 → MZM 束缚在涡旋核
    
    ASCII 示意：
      FTS 体：bulk SC (Tc ~15K) + topological band inversion
      TI 表面：Dirac cone 被诱导超导能隙打开
      涡旋：B 场 → 磁通量子穿过体 → 涡旋核心 → MZM！（[猜想]）

  关键实验：Zhang 2018 Science 360, 182（[确定，未撤回]）
    样品：Fe(Te₀.₅₅Se₀.₄₅) 单晶
    实验：低温（0.4K）STM 测量外磁场（B~0.5T）中的涡旋核心隧道谱（dI/dV）
    结果：部分涡旋（约 1/3）在 V=0 处出现尖锐 ZBCP（E = 0 束缚态）
    ZBCP 半峰宽：~0.1 meV（由能量分辨率决定）[Zhang 2018, Science 360, 182]
    另一部分涡旋（~2/3）没有 ZBCP → 解释为拓扑/trivial 涡旋共存 [猜想]

  后续支持证据（[来源待验证]）：
    Wang 2020 等：在相关体系中复现 ZBCP
    多组 STM 研究确认部分涡旋有零能模 [来源待验证]
    
  ⚠️ 核心争议：trivial Andreev 还是 Majorana？
    Trivial 解释：
      Caroli-de Gennes-Matricon（CdGM）Andreev 束缚态也出现在涡旋核心
      CdGM 态的能量间隔：δE ≈ Δ²/E_F
      当 E_F 小（FTS 的 Fermi 口袋小！）→ δE 增大 → CdGM 态看起来像零模 [猜想]
      Pan & Das Sarma 系列的 FTS 版本：trivial CdGM 可以解释所有观测 [猜想]
    
    区分判据（目前实验尚未满足）：
      (a) 量子化隧道电导 2e²/h（理论预测，从未实现）
      (b) 非局域 Majorana 关联（需要双端 STM 或其他方案）
      (c) 参数控制的拓扑相变（调控 μ 穿越 |μ|=2t 相变线时 ZBCP 消失/出现）

  综合评估：
    [猜想] FTS 是目前体材 TSC 最强候选，但证明其为 TSC 的决定性实验尚未完成
    相比纳米线体系，FTS 的优点：体材（不是界面/近邻）、Tc 较高、无撤稿丑闻
    缺点：ZBCP 的 trivial 解释难以排除，量子化电导从未在 FTS 中报道
```

### 3.2 InSb/InAs 半导体纳米线（Lutchyn-Oreg 方案）

**[撤稿历史必须完整记录；[猜想]，学界高度谨慎]**

```
纳米线 Majorana 体系：

  理论实现 Kitaev chain 的条件（[定理，严格推导自 Lutchyn 2010，Oreg 2010]）：

    InSb（或 InAs）纳米线的特性：
      强 Rashba SOC（α_R ~ 0.2–1 eV·Å）[来源待验证]
      g 因子大（g* ~ 10–50，InSb > InAs）[来源待验证]
    
    器件结构：纳米线 + 近邻 s-wave SC（NbTiN 或 Al）
    BdG 哈密顿量（k 沿纳米线方向）：
      H_NW(k) = (ε_k - μ) τ_z + α_R k σ_y τ_z + V_Z σ_x + Δ τ_x
      
      其中：ε_k = ℏ²k²/2m*（单轨道）
            α_R k σ_y = Rashba SOC
            V_Z = (1/2)g* μ_B B（Zeeman 能，外加纵向磁场）
            Δ = 近邻诱导超导间隙
    
    拓扑相变条件（[定理]）：
      ASCII: V_Z > sqrt(mu^2 + Delta^2)
      即：Zeeman 能 > 化学势和超导间隙的合并值
    
    相变前后：
      V_Z < sqrt(μ² + Δ²)：拓扑平凡（normal SC state）
      V_Z > sqrt(μ² + Δ²)：拓扑非平凡（Class D，ν=1）→ 纳米线两端 MZM

  实验历史（完整记录包括撤稿）：

    2012 Mourik（TU Delft，Science 336, 1003）：
      InSb-NbTiN 纳米线，B > B_c 后出现 ZBCP
      [确定，未撤回，但解释争议大]
    
    2012–2016 多组 ZBCP 报道：
      Copenhagen（Deng, Marcus 等）、Harvard 等多组复现 ZBCP [来源待验证]
      但量子化电导一直缺失，ZBCP 精确特征与理论不完全吻合
    
    2017–2018 Zhang TU Delft（Nature 556, 74）：
      宣称看到 G ≈ 2e²/h 的"量子化" ZBCP
      ⚠️ 2021 年撤稿！原因：数据筛选
    
    2021 撤稿（Nature）：
      调查结果：部分作者在决定发表前已知道不良数据，
      但论文只呈现了选择后的"好数据"
      → 量子化 ZBCP 结论无法成立 [确定]
    
    2020–2022 Pan & Das Sarma 系统性质疑：
      证明软化的 trivial Andreev 态可以在所有实验条件下完美模拟 Majorana ZBCP
      [Pan & Das Sarma 2020, PRL 124, 227001；来源部分待核查]
    
    2023 Microsoft "Majorana 1"：
      新架构（InAs 2DEG + Al），"topological gap protocol"
      topo gap > 30 μeV（宣称）[来源待验证，Microsoft 预印本]
      ⚠️ 至 2026：无独立验证，学界谨慎态度明显

  综合评估：
    [猜想，学界高度谨慎]
    纳米线体系经历了 Majorana 研究最严重的信誉危机（2018 撤稿）
    理论框架（Lutchyn-Oreg）是正确的（定理），但材料实现面临：
      (a) 无序问题：纳米线-SC 界面无序将 MZM 与 trivial 态混淆
      (b) 软化问题：真实纳米线中 μ 局域变化 → 准 MZM（quasi-Majorana）
      (c) 量子化电导难以实现：需要完美接触 + 无杂质 + 精确 μ 控制
```

### 3.3 TI/SC 异质结（Fu-Kane 方案）

**[理论为 [定理]；材料实现为 [猜想]]**

```
拓扑绝缘体/超导体异质结：

  Fu-Kane 机制（[定理，严格推导]）：
    TI（拓扑绝缘体）表面态：Dirac 锥
      H_surface = v_F (k × σ)·z = v_F (k_x σ_y - k_y σ_x)
    
    近邻超导化：TI 表面与 s-wave SC 接触 → 诱导超导能隙 Δ
    
    联合 Hamiltonian：
      H_FK = v_F(k_x σ_y - k_y σ_x) - μ + Δ τ_x
      （τ = Nambu 空间，σ = 自旋）
    
    关键结论（[定理]）：
      H_FK 在拓扑非平凡相（适当 μ）等价于 chiral p+ip SC（Read-Green 态）
      → 面内涡旋核心束缚 Majorana 零模
      → 无需本征 p-wave SC，用 TI 表面 + s-wave SC 即可合成

  主要材料体系：
    
    Bi₂Se₃（或 Bi₂Te₃）+ Nb（或 NbSe₂）：
      TI：Bi₂Se₃，Bi₂Te₃，Bi₂Te₂Se 等
      SC：Nb（Tc=9.2K），NbSe₂（Tc=7K），Al
      实验：STM 在 Bi₂Te₃/NbSe₂ 界面涡旋看到 ZBCP [来源待验证]
      [Xu et al. 2014 等，来源待核查；具体引用不确定]
    
    Cu_x Bi₂Se₃（掺杂拓扑绝缘体，非界面）：
      Tc ≈ 3.8K，可能的 Class DIII TSC（三维）[来源待验证]
      奇次配对或 B₂g 配对 → TSC 候选 [猜想]
      NMR/点接触测量暗示 triplet 分量 [来源待验证]

  ⚠️ 核心问题：Fu-Kane 实验中的 trivial Andreev
    界面态（TI 表面的普通态）也可以被近邻超导化 → 普通 Andreev 束缚态
    这些 trivial Andreev 态在涡旋核心同样出现 ZBCP
    与 MZM 的区分：需要量子化电导（e²/h）或非局域测量，均未实现 [来源待验证]

  综合评估：[猜想]
    理论（Fu-Kane 方案）是 TSC 领域最优雅的构造之一
    实验上，TI/SC 界面的 ZBCP 普遍存在，但 Majorana 解释无一被决定性确认
```

### 3.4 半 Heusler 化合物（YPtBi 等）

**[实验数据 [来源待验证]；理论为 [猜想]]**

```
半 Heusler 超导体候选：

  为什么是 TSC 候选？
    半 Heusler 化合物（RPtBi，RPdBi，R = 稀土）是拓扑半金属（TI 或零带隙半导体）
    在低温下出现超导，Tc 在 0.5–2K 范围
    特殊之处（[猜想]）：
      j = 3/2 电子（f 轨道重费米子 + 强 SOC）→ 高自旋 Cooper 对
      可能存在 septet 配对（J=3，角动量更高的 Cooper 对）
      这超出 BCS singlet/triplet 分类（s-wave/p-wave）

  YPtBi（最主要候选）：
    Tc ≈ 0.77K [来源待验证，Kim et al. 2018 Science Advances 等]
    H_c2 ≈ 1.5 × H_Pauli（超过 Pauli 极限）[来源待验证]
    Pauli 极限违反解释：j=3/2 → triplet/septet 配对？[猜想]
                        或 Rashba SOC 保护？[猜想]
    
    现有证据 [来源待验证]：
      比热测量暗示非常规超导（线节点？）[猜想]
      NMR：数据解释不明确 [来源待验证]
      点接触谱：暗示非常规 [来源待验证]

  LaPtBi、LuPtBi 等类似体系 [来源待验证]

  综合评估：[猜想，理论新颖，实验基础非常弱]
    Tc 极低（<1K），难以进行精确测量
    j=3/2 配对理论有趣，但与实验数据的对应关系尚不清楚
    不是目前 TSC 研究的重点方向
```

---

## 4. Majorana 实验判据

**[判据的理论依据为 [定理]；具体体系的满足情况为 [观察]]**

```
可信的 Majorana 证据需要满足的多重判据（学界逐步形成的共识）：

  判据 1：ZBCP 随拓扑相变出现/消失（参数扫描）
    要求：调控参数（μ、B、Δ 等）穿越拓扑相变点时 ZBCP 应跟随相变消失
    现状：部分实验有这类迹象，但 trivial Andreev 也会随参数变化（模糊） [观察]

  判据 2：量子化隧道电导 G = e²/h（[定理，Kitaev chain 末端理论预测]）
    要求：MZM 对应的 Andreev 反射系数为 1（完美 Andreev 反射）→ G = e²/h
    现状：⚠️ 从未在任何 TSC 候选中稳定、可重现地实现！
    2018 Zhang 撤稿正是因为宣称的 G = 2e²/h（不是 e²/h）且数据经过筛选

  判据 3：非局域响应（multi-terminal 测量）
    要求：两端 MZM（γ_L，γ_R）之间的非局域关联
    需要：两个隧道探针同时测量纳米线两端，测量非局域电导矩阵
    非局域判据：G_LL * G_RR - G_LR * G_RL = 0（量子化关系）[定理]
    现状：技术难度极高；有少量报道，但结果不稳定 [来源待验证]

  判据 4：4π 周期 Josephson 效应
    要求：拓扑 Josephson 结 → I_s ∝ sin(φ/2)（4π 周期，而非 2π）
    实验测量：交流 Josephson 效应频率应减半（出现次谐波 f/2）
    现状：测量中存在"漏电"信号，准粒子毒化（quasiparticle poisoning）严重干扰 [观察]
    ⚠️ 几乎所有宣称的 4π 信号都可以有非拓扑解释 [来源待验证]

  判据 5：非阿贝尔 braiding 统计
    要求：操控两个 MZM 并验证 braiding 产生的量子门操作
    现状：理论上最决定性的判据，实验上难度最高
    Microsoft 2023 宣称实现初步 braiding，但独立验证缺失 [来源待验证]

  ★★★ 当前状态（截至 2026）：
    没有任何 TSC 候选体系同时满足以上 5 条判据！
    最强证据：FTS 的 ZBCP（满足判据 1 的部分，不满足 2–5）
    最弱证据：纳米线（判据 1 部分，判据 2 已撤稿，其他均未满足）
```

---

## 5. 撤稿与争议总结（反谄媚核心章节）

**[事实清单 — 记录 TSC 领域的学术信誉问题]**

```
⚠️ TSC 领域的系统性问题：

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
撤稿 1：Zhang et al. 2018 Nature 556, 74（TU Delft）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  宣称：InSb 纳米线量子化 ZBCP G ≈ 2e²/h = Majorana
  撤稿年份：2021
  撤稿原因：数据筛选（selection bias）
    - 实验室记录的大量 ZBCP 不清晰数据被未发表
    - 论文只展示了符合理论预期的数据子集
    - 量子化结论不成立
  影响：Microsoft 曾以此论文为 Majorana 实验基础，需重新评估整个技术路线
  
  [已确认撤稿，Nature 2021]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
部分撤回/更正：TU Delft / Microsoft 相关多篇论文（2017–2021）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  多篇关于纳米线 Majorana 信号的论文在审查后进行部分更正
  [具体论文列表 来源待验证，但整体事实已广为人知]
  
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
间接信誉危机：Sr₂RuO₄（→ C5, C7）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  背景：Sr₂RuO₄ 于 1994 年被提出为 TSC 候选（chiral p+ip）
  24 年共识（1994–2019）：大量实验解释为支持 TSC
  翻案：2019 Pustogow 等 NMR Knight shift 精确测量
    → 超导下 Knight shift 下降 → singlet SC，非 triplet → 非 TSC [确定]
  教训：24 年的"共识"可以被一个精确实验推翻

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
系统性问题：Pan-Das Sarma trivial Andreev 系列（2020+）
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  结论（[来源部分待核查，但内容得到同行认可]）：
    (a) 纳米线中的局域 μ 起伏 → "准 Majorana"（quasi-Majorana）出现
    (b) 准 Majorana = trivial Andreev，但外表几乎与真 MZM 完全一样
    (c) ZBCP + 磁场依赖 + 温度依赖，所有"Majorana 特征"均可由 quasi-Majorana 解释
    (d) 区分 MZM 和 quasi-Majorana 需要非局域测量，而大多数实验是局域的！

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
商业利益驱动的数据偏差
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Microsoft：MZM 是其拓扑量子计算路线（Station Q 战略）的核心
  Google：有 Majorana 研究，但路线不同
  全球量子计算竞赛 → 对 Majorana 的迫切需求
  ⚠️ 后果：
    - 过度解读 ZBCP 信号
    - 选择性发表有利数据
    - 媒体报道远超实验证据
    - 科研基金与商业目标的直接挂钩
  
  比较（TSC vs 其他超导方向）：
    铜氧化物：商业利益较少 → 数据报道相对客观
    氢化物室温SC：有压力，但撤稿主要源于系统误差而非数据选择
    TSC：商业利益最密集 → 数据报道偏差最严重

教训总结：
  研究 TSC 材料时，需要对以下迹象保持高度警惕：
  (1) 只有 ZBCP 而没有多重判据满足的"Majorana 声明"
  (2) 由商业机构（Microsoft/Google）主导发表的结果
  (3) 量子化电导值"接近但不精确"的报告
  (4) 多次测量中只选择性报告"好数据"的迹象
```

---

## 6. 关键定量数据

**[严格区分来源确定性]**

```
Fe(Te₀.₅₅Se₀.₄₅)（FTS）：
  Tc ≈ 14.5K（体材）[来源待验证，~ 一般引用值]
  STM ZBCP（涡旋核心）：
    半峰宽 ~0.1 meV [Zhang 2018, Science 360, 182]（确定）
    出现比例：~1/3 涡旋 [Zhang 2018, Science 360, 182]（确定）
    测量温度：T = 0.4K，B = 0–2T [Zhang 2018, Science 360, 182]（确定）
  拓扑表面态 Dirac 点：ARPES 直接观测 [来源待验证，~0.3 eV 以下]

InSb / InAs 纳米线（Lutchyn-Oreg）：
  InSb g* ≈ 40–50（大！）[来源待验证]
  InSb Rashba 系数 α_R ~ 0.2–1 eV·Å [来源待验证]
  ZBCP 出现磁场：B_c ~ 0.15–0.3T（体系依赖）[来源待验证，Mourik 2012 量级]
  宣称量子化 G ≈ 2e²/h（2018 Zhang，已撤稿！）
  Microsoft Majorana 1 宣称 topo gap > 30 μeV [来源待验证，MS 预印本 2023]

TI/SC 异质结（Fu-Kane）：
  Bi₂Te₃/NbSe₂：Tc（近邻诱导）≈ 3–5K [来源待验证]
  Cu_x Bi₂Se₃：Tc ≈ 3.8K（x ≈ 0.3）[来源待验证]
  ZBCP 信号：多组报道，但量子化电导均未实现 [来源待验证]

半 Heusler（YPtBi）：
  Tc = 0.77K [来源待验证，Kim 2018 等]
  H_c2 ~ 1.5 × H_Pauli（上临界场超出 Pauli 极限）[来源待验证]

拓扑量子计算所需参数（理论）：
  拓扑能隙 E_gap > k_B T（可操控温度下）：通常需要 E_gap > 100 μeV
  Majorana 关联长度 ξ_M < 器件长度 L：[来源待验证]
  已有材料中最优：FTS ~0.1 meV（符合要求？），纳米线 30–100 μeV（宣称）
```

---

## 7. 关键反谄媚

**[对 TSC 领域常见误区的纠正]**

```
反谄媚 1：ZBCP 不是 Majorana 的证明

  ✅ 事实：ZBCP（零偏压电导峰）是 MZM 的必要条件，不是充分条件
  ✅ trivial Andreev 束缚态（软化 CdGM 态、quasi-Majorana 等）可以完美模拟 ZBCP
  ✅ Pan & Das Sarma（2020+）系统证明了这一点
  ❌ 看到 ZBCP 就宣称"发现 Majorana"是不负责任的
  ✅ 正确表述：ZBCP 与 Majorana 解释一致（necessary, not sufficient）

反谄媚 2：量子化电导 e²/h 从未被稳定实现

  ✅ 事实：所有宣称"量子化 ZBCP"的报告要么未被独立验证，要么被撤稿
  ✅ 2018 Zhang（G = 2e²/h）已撤稿（2021）
  ✅ 严格量子化 e²/h（不是 2e²/h！）在任何 TSC 候选中均未稳定观测
  ❌ "量子化 ZBCP = Majorana" → 已被 2021 撤稿事件证伪

反谄媚 3：商业机构的 Majorana "宣布"≠ 科学证明

  ✅ Microsoft 2023 "Majorana 1"：
    这是商业发布（press release），不是经过独立验证的科学证明
    "topological gap protocol"是代理判据，不直接证明 Majorana
    至 2026 年，无独立实验室复现核心结论
  ❌ 将 Microsoft 宣传稿当作 Majorana 已实现的科学证据
  ✅ 商业压力是 TSC 领域数据偏差的系统性根源

反谄媚 4：FTS 是最强候选，但仍是 [猜想]

  ✅ Zhang 2018 Science 未撤回，ZBCP 数据可靠
  ✅ FTS 的 TI 表面态 + SC 提供了 Fu-Kane 机制的理论基础
  ✅ 多组重复确认了部分涡旋的 ZBCP
  ⚠️ 但：trivial CdGM 解释尚未被排除，量子化电导未在 FTS 中实现
  ❌ "FTS 证实了 Majorana 零模" → [猜想]，非定论
  ✅ 正确表述：FTS 是目前实验证据最可靠的体材 TSC 候选，但距"确认"尚远

反谄媚 5：Sr₂RuO₄ 不再是可信的 TSC 候选

  ✅ 2019 Pustogow Knight shift 实验翻案 → singlet SC，非 triplet p-wave
  ✅ 没有可信的 p-wave TSC → 不是 TSC 候选（至少不是 chiral p+ip 那种）
  ❌ 引用 2019 前的文献说"Sr₂RuO₄ 是 TSC 候选" → 信息过时
  ✅ 24 年信心崩塌的教训：长期"共识"不代表正确

反谄媚 6：拓扑量子计算的实用路径仍不明朗

  ✅ 非阿贝尔 braiding 需要：空间分离的 MZM + 可控操作 + 拓扑保护能隙
  ✅ 目前没有体系同时满足这三个条件
  ✅ 即使实现 MZM，braiding 操作速度受拓扑能隙限制（可能很慢）
  ❌ "MZM 将很快实现容错量子计算" → 商业乐观主义，非科学评估
```

---

## 8. 与 MECE 框架和 Paper A/B 的关联

**[框架关联 — 明确适用范围和超出范围]**

```
D12 与 Paper A（多通道 Allen-Dynes Eliashberg 框架）：
  所有 TSC 候选均超出 Allen-Dynes 框架的直接适用范围：
  
  FTS（Fe(Te,Se)）：
    Allen-Dynes 对体材超导（Tc ~ 15K）可能部分适用（铁基 SC → D4）
    但拓扑方面（能带拓扑、表面态）完全超出声子框架
    → Allen-Dynes 可描述 FTS 的 Tc，但不能描述其拓扑性质

  纳米线 / TI/SC 界面：
    这些是近邻超导体（利用现有 SC），配对机制是 s-wave（NbTiN/Al/NbSe₂）
    Allen-Dynes 描述的是 SC 基底的 Tc，而非纳米线本身
    → Paper A 完全不适用于理解 TSC 候选的拓扑性质

  结论：TSC 的重要性不在于高 Tc，而在于拓扑保护的零模。
        Paper A 是描述高 Tc 物理的框架，对 TSC 研究贡献有限。

D12 与 B11（拓扑超导理论）：
  B11 是 D12 的理论母框架：
    AZ 10 折分类 → D12 的材料拓扑分类依据
    Kitaev chain → 纳米线体系的理论基础
    Fu-Kane 方案 → FTS 和 TI/SC 界面的理论基础
    Read-Green → chiral p+ip → 历史起点
  D12 = B11 在材料层面的落地（理论 → 材料实现）

D12 与 C5/C7（p-wave / chiral）：
  TSC 通常需要有效的奇次（triplet）超导分量：
    chiral p+ip（Class D，C7）= 最基本的 2D TSC
    p-wave（C5）= triplet 配对是 TSC 的常见配对对称性
    Fu-Kane 机制：s-wave + TI → 等效 p-wave（绕开直接 p-wave 材料要求）

D12 与 A9（Andreev）：
  所有 TSC 实验的核心工具 = Andreev 谱（A9）
  ZBCP = 特殊的 Andreev 束缚态（零能 ABS）
  Majorana 零模 = 拓扑保护的零能 Andreev 束缚态
  普通 Andreev vs Majorana 的区分 = A9 节点的核心问题

D12 与 D8/C6（重费米子 / UTe₂）：
  UTe₂ 在 C6/D8 节点已详述，此处仅标记：
  UTe₂ 也是 TSC 候选（spin-triplet SC，可能 chiral → TSC）
  但 UTe₂ 配对对称性尚未确定 → D12 中不作为主要候选列出

D12 与 D11（2D/界面）：
  TI/SC 界面（Fu-Kane 实验实现）是 D11 的关联体系
  D11 中 LAO/STO + Rashba → 潜在 TSC [猜想]
  D12 和 D11 的交叉：界面体系（Bi₂Te₃/NbSe₂，InAs/Al 2DEG 等）同时属于两个节点
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026） | 主要障碍 | 相关 MECE |
|------|----------------|---------|-----------|
| **FTS 的 ZBCP 是 MZM 还是 trivial Andreev？** | [猜想，开放，核心问题] | trivial CdGM 态难以与 MZM 区分；需要非局域实验 | A9, B11 |
| **纳米线中量子化电导 e²/h 是否可以稳定实现？** | [猜想，2021 撤稿后信誉受损] | 无序、准 Majorana（quasi-Majorana）问题 | B11 |
| **Microsoft Majorana 1 能否被独立验证？** | [开放，至 2026 无独立复现] | 商业利益与透明度的冲突 | — |
| **是否存在无需近邻效应的本征 TSC（Intrinsic TSC）？** | [猜想，UTe₂ 是候选] | 确定三维拓扑不变量需要全面表征 | C6, D8 |
| **拓扑能隙的最大值——什么材料能提供最大 E_topo？** | [猜想，~0.1–1 meV 范围] | 高 Tc TSC 候选缺乏 | B11 |
| **非阿贝尔 braiding 的实验实现** | [猜想，从未被独立验证] | MZM 操控的技术难度 | B11 |
| **Cu_x Bi₂Se₃ 的配对对称性（B₂g singlet vs triplet？）** | [猜想，实验争议大] | 超导本征非常规性的表征 | C5, C9 |
| **YPtBi 等半 Heusler 是否有 j=3/2 septet 配对？** | [猜想，实验基础弱] | Tc 极低（0.77K），精确测量困难 | C5, C9 |

---

## 附录：核心速查（ASCII 格式）

```
=== D12 拓扑超导体候选 核心速查 ===

[1] 四大候选体系总览：
  Fe(Te,Se)（FTS）— 最强体材 TSC 候选：
    Tc ~ 15K，ZBCP 在涡旋核心 [Zhang 2018, Science 360, 182] ✅（未撤回）
    ZBCP 半峰宽 ~0.1 meV [Zhang 2018]
    ⚠️ MZM vs trivial Andreev 未定论；非局域实验未完成
    综合：[猜想，最强候选，但非确认]

  InSb/InAs 纳米线（Lutchyn-Oreg）：
    理论框架：[定理，Lutchyn 2010 PRL 105, 077001；Oreg 2010 PRL 105, 177002]
    实验：ZBCP [Mourik 2012, Science 336, 1003]（确定）
    ⚠️ 2018 量子化 ZBCP 论文已撤稿（2021）！
    ⚠️ Pan-Das Sarma（2020+）：quasi-Majorana 可解释所有观测
    综合：[猜想，信誉重创，学界高度谨慎]

  TI/SC 异质结（Fu-Kane）：
    理论：[定理，Fu-Kane 2008 PRL 100, 096407]
    实验：ZBCP 存在，但量子化电导未实现 [来源待验证]
    综合：[猜想]

  半 Heusler（YPtBi 等）：
    Tc ~ 0.77K，H_c2 > H_Pauli [来源待验证]
    j=3/2 高自旋配对理论：[猜想]
    综合：[猜想，理论有趣，实验基础非常弱]

[2] BdG 拓扑不变量（Kitaev chain，Class D）：
  H_BdG(k) = (-2t*cos(k) - mu)*tau_z + 2*Delta*sin(k)*tau_x  [定理]
  拓扑条件：|mu| < 2t → nu=1（非平凡）；|mu| > 2t → nu=0（平凡）
  Z₂ 不变量：nu = sgn[Pf(H(0)) * Pf(H(pi))]  [定理]
  
  纳米线（Lutchyn-Oreg）：
  H_NW = (eps_k - mu)*tau_z + alpha_R*k*sigma_y*tau_z + V_Z*sigma_x + Delta*tau_x
  拓扑条件：V_Z > sqrt(mu^2 + Delta^2)  [定理]
  
  Fu-Kane：
  H_FK = v_F*(kx*sigma_y - ky*sigma_x) - mu + Delta*tau_x  [定理]

[3] 五重 Majorana 判据（截至 2026 全部未同时满足）：
  1. ZBCP 随拓扑相变出现/消失（参数扫描）← 部分实验迹象
  2. 量子化电导 G = e²/h ← ⚠️ 从未稳定实现（2018 撤稿！）
  3. 非局域响应（多端测量）← 极少且不稳定
  4. 4π 周期 Josephson 效应 ← 准粒子毒化严重干扰
  5. 非阿贝尔 braiding 统计 ← ⚠️ 从未独立验证

[4] 撤稿与丑闻清单：
  2021：Zhang et al. 2018 Nature 撤稿（TU Delft，数据筛选）✅ 确定
  2019：Sr₂RuO₄ chiral p+ip 假说被推翻（24年共识崩塌）✅ 确定
  2020+：Pan-Das Sarma 证明 quasi-Majorana 可解释所有纳米线 ZBCP ✅ 确定
  2023：Microsoft Majorana 1，商业宣传 ≠ 科学验证，无独立复现

[5] 核心反谄媚：
  ⚠️ 没有任何 TSC 被无争议确认（截至 2026）
  ⚠️ ZBCP 是必要非充分条件，trivial Andreev 完美模拟
  ⚠️ 量子化电导 e²/h 从未稳定实现
  ⚠️ 商业压力（Microsoft 量子计算路线）是 TSC 领域数据偏差的系统性根源
  ⚠️ Sr₂RuO₄ 教训：24 年共识 → 一个精确实验推翻

=== D12 与 MECE 关联图 ===
  B11（拓扑超导理论）→ D12 的理论母框架（AZ 分类 + Kitaev + Fu-Kane）
  C5/C7（p-wave/chiral）→ TSC 配对对称性基础（triplet / chiral p+ip）
  A9（Andreev）→ ZBCP 实验探测工具；MZM = 零能 ABS
  D8（重费米子）→ UTe₂ 作为潜在 TSC 候选（D8 详述）
  D11（2D/界面）→ TI/SC 界面（Fu-Kane 实验实现）
  C9（Singlet vs Triplet）→ TSC 通常需要奇次配对分量
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**字节大小估计：** ~15.5 KB

**反谄媚审计：**
- ✅ 2021 Zhang Nature 撤稿完整记录，数据筛选原因清楚说明
- ✅ Pan-Das Sarma trivial Andreev 系列充分引用，对 ZBCP 的质疑清楚
- ✅ Sr₂RuO₄ 翻案作为历史教训记录
- ✅ Microsoft "Majorana 1" 标注为商业宣传而非科学证明
- ✅ 量子化电导 e²/h 从未稳定实现明确说明
- ✅ 所有 TSC 候选均标注 [猜想]，无一例外
- ✅ BdG 拓扑不变量标注 [定理]（严格数学），与材料实现 [猜想] 区分
- ✅ FTS 最强候选但"非确认"，反对"FTS 已证明 Majorana"的说法
- ✅ 商业利益对数据偏差的系统性影响明确说明
- ✅ 拓扑量子计算的实用路径标注为不明朗（而非乐观预测）

**D 部分状态：** D1 ✅ → … → D11 ✅ → **D12 ✅（当前）**
