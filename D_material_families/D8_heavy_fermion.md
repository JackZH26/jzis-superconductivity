# D8. 重费米子超导体 — QCP 附近的 f 电子非常规超导，Kondo 效应与磁序的边疆

**MECE 编号：** D8
**关联 MECE：**
- B3（自旋涨落 AFM — CeCu₂Si₂/CeCoIn₅ 的 d-wave 来自 AFM-QCP 上方的量子临界涨落）
- B4（自旋涨落 FM — URhGe/UCoGe 的 triplet SC 由 FM 涨落直接驱动；UTe₂ 候选）
- B10（Hund's coupling — 4f/5f 强关联、Hund 耦合与 Kondo 屏蔽的竞争，重 FL 形成）
- B14（Mottness — 重费米子是 Mott 绝缘体的 f 电子极限；Kondo 晶格 ~ 强关联 Hubbard）
- C3（d_x²-y² wave — CeCu₂Si₂ 和 CeCoIn₅ 的 d-wave 配对；热导率节点确认）
- C5（p-wave — UTe₂ 和 URhGe/UCoGe 的 triplet 候选；Sr₂RuO₄ 教训的直接关联）
- C6（f-wave — UPt₃ E₂u f-wave 候选；35 年争议的核心材料）
- C9（Singlet vs Triplet — 重费米子同时包含 singlet（Ce 基）和 triplet（U 基）案例）

**层级关系：** D8 是非常规超导研究中**概念最复杂**的材料家族：Tc 极低（<5K），完全无实用价值，但作为量子临界配对机制的**清洁实验室**无可替代。Kondo 物理 + QCP + 非常规配对三个复杂物理同时出现，是理论物理学家的天堂，是工程师的噩梦。
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 Steglich 1979 PRL、Mathur 1998 Nature、Petrovic 2001 JPCM、Ran 2019 Science 等核心文献；数值标注来源，多数待精确核查）

⚠️ **核心诚实声明：重费米子超导体的 Tc 全部低于 5K，没有任何实际应用价值。研究价值完全在于机制：它是迄今为止 QCP 驱动非常规超导假说最直接的实验体系。但即使是这个假说，机制争议至今未决——QCP 驱动 SC 是 [猜想]，不是 [定理]。UTe₂ 的 triplet 标签尤其危险，Sr₂RuO₄ 24 年翻案教训必须时刻铭记。**

---

## 1. 物理定义与核心思想

### 1.1 重费米液体：f 电子如何变重

**[定理 — 重费米液体的实验特征（比热、磁化率、电阻率）已有大量测量确认；微观 Kondo 晶格理论是 [猜想] 层级但高度可信]**

```
重费米子体系的物理起源：

4f/5f 轨道特性（[定理]）：
  Ce (4f¹): 角动量 J = 5/2，局域磁矩可与传导电子发生 Kondo 屏蔽
  U  (5f²/5f³): 5f 更弥散（轨道更大），局域-巡游二象性更强
  Yb (4f¹³): 空穴类 Ce，4f¹³ ≡ 4f 空穴，同样有 Kondo 物理
  Pr (4f²): 非 Kramers 离子，四极矩 Kondo 可能，更罕见
  
  f 轨道的特殊性：
    4f（Ce, Yb）：原子内层轨道，离子半径小，与传导带重叠弱 → 强局域性倾向
    5f（U, Np）：轨道更大，f 电子可部分巡游 → 局域-巡游二象性更强
    关键：f 电子不完全局域（否则 = 磁绝缘体），也不完全巡游（否则 = 普通金属）
    → 边界区域 = 重费米子

Kondo 效应与屏蔽（[定理 — Anderson 1961, Kondo 1964 微观理论；重费米子 Kondo 晶格是推广]）：
  单杂质 Kondo 效应：
    局域磁矩 S 与传导电子耦合 J_K（反铁磁）
    低温 T < T_K 时：磁矩被传导电子云屏蔽
    Kondo 温度：T_K ~ W × exp(-1/(J_K × N(E_F)))
    
    LaTeX: T_K \sim W \exp\!\left(-\frac{1}{J_K N(E_F)}\right)
    ASCII: T_K ~ W * exp(-1 / (J_K * N(EF)))
    
    其中 W ~ 传导带宽度，N(EF) ~ 传导带 DOS
    物理含义：J_K × N(EF) 越大，屏蔽越强，T_K 越高

  Kondo 晶格推广（Doniach 1977 Physica B，[猜想层级，但广被接受]）：
    f 电子在每个晶格格点形成 Kondo 中心
    重费米子金属 = Kondo 晶格 = 全部格点上磁矩均被屏蔽的相干状态
    屏蔽后的准粒子 = 传导电子 + 局域 f 电子的复合体
    → 有效质量 m* >> m_e（带宽被压缩，m* ∝ 1/W_renorm）

重费米液体的实验特征（[定理，多材料验证]）：
  比热系数 γ = C/T（T→0）：~ 100–1000 mJ/(mol·K²)（普通金属 ~ 1-10 mJ/(mol·K²)）
  磁化率 χ：T 无关（Pauli 型），数值大（磁矩未完全消失）
  电阻率：ρ ~ ρ_0 + AT²（Fermi 液体行为），A 系数大（A ∝ m*²）
  Kadowaki-Woods 比：A/γ² ~ 10⁻⁵ μΩcm(mol·K/mJ)² [定理，普适比值]
  有效质量：m*/m_e ~ 100–1000（最重的量子准粒子！）
```

### 1.2 Doniach 相图：重费米子的宏观相图

**[猜想 — Doniach 1977 提出，理论框架被广泛接受，细节仍有争议]**

```
Doniach 相图中的两个竞争能量尺度：

  RKKY 耦合（Ruderman-Kittel-Kasuya-Yosida，[定理 — 摄动论结果]）：
    f 矩之间通过传导电子的间接交换
    LaTeX: T_{RKKY} \sim J_K^2 N(E_F)
    ASCII: T_RKKY ~ J_K^2 * N(EF)
    特征：J_K 小时 T_RKKY 小，但 T_K 更小（指数衰减）→ RKKY 胜 → 磁序

  Kondo 屏蔽（[定理 — 单杂质级]）：
    LaTeX: T_K \sim \exp(-1/(J_K N(E_F)))
    ASCII: T_K ~ exp(-1/(J_K*N(EF)))
    特征：J_K 大时 T_K 快速增大 → Kondo 胜 → 重费米液体

  两个尺度的竞争（Doniach 1977）：
    J_K 小（左侧）：T_RKKY > T_K → 磁有序（AFM 或 FM）
    J_K 大（右侧）：T_K > T_RKKY → Kondo 屏蔽 → 重费米液体金属
    交叉点：T_RKKY ~ T_K → 量子临界点（QCP）！
    
    ASCII 相图示意：

    T |
      |  AFM 序           重费米液体
      |    \              /
   TN|     \  SC dome  /
      |      \_________/
      |          ↑
      |          QCP
      |________________
                      J_K (或压力 p，掺杂 x)

  QCP 的物理意义：
    TN → 0 处的零温二阶相变（量子相变）
    T > 0 时：量子临界区（量子涨落主导，非 FL 行为）
    非常规超导 SC dome 通常出现在 QCP 附近 [猜想，直接证据最干净体系：CeIn₃]

Hertz-Moriya-Millis (HMM) 量子临界理论（[猜想，争议较大]）：
  思路：QCP 处 AFM 临界涨落（波矢 Q）介导非常规配对
  机制：V_eff(q,ω) ~ -χ(q,ω)（超级类比：声子 → AFM 涨落）
  预测：AFM QCP → d-wave 配对（配对势在 Q 散射的准粒子间最大）
  问题 1：HMM 理论忽略了费米子模式对临界点本身的反作用（non-Gaussian 修正）
  问题 2：很多重费米子的 SC 区域比 QCP 宽得多，不像"单纯 QCP 驱动"
  结论：HMM 是目前最好的定量框架，但不是确定的机制 [猜想]
```

### 1.3 f 电子局域-巡游二象性

**[观察 — 实验现象明确；理论解释争议]**

```
局域-巡游二象性的表现：

  静态描述：
    ARPES 看不到干净的 f 带（太窄、相干峰弱）[观察]
    de Haas-van Alphen（dHvA）测量到大费米面（包含 f 电子）[定理，测量确定]
    → 矛盾：ARPES（快探针）看到局域 f，dHvA（低能平衡）看到巡游 f
    解释：Kondo 共振在 T << T_K 才形成；ARPES 在 T >> T_K 时 f 仍局域

  动态描述（轨道涨落）：
    在 T ~ T_K 时：f 电子在局域磁矩和巡游准粒子之间快速涨落
    这种涨落本身可以成为非常规配对的媒介 [猜想，轨道涨落机制]
    
  Ce vs U 的差异：
    Ce（4f¹）：通常 T_K ~ 1–100K，4f 轨道强局域，Kondo 晶格图像更可靠
    U（5f²/³）：5f 更弥散，轨道有部分巡游成分，"双态 f 模型"更合适
    UTe₂：U 的 5f 本质使配对对称性判断极为困难 → 这正是 UTe₂ 争议的根源
```

---

## 2. 历史关键节点

**[历史 — 有文献来源的事件；数值标注来源]**

```
★★★ 1979：Steglich et al.（TU Darmstadt，Germany）
  发现 CeCu₂Si₂ 在 Tc ≈ 0.6K 处超导
  [Steglich et al. 1979, PRL 43, 1892]（确定）
  ★ 划时代意义：
    - 第一个重费米子超导体（也是第一个非常规超导体！）
    - Tc 极低，但超导在 m* ~ 200-400 m_e 的"重"系统中出现本身就震惊物理界
    - 启示：Cooper 对可以由非声子机制形成（后来的 d-wave AFM 涨落图像）
    - 至今无法确认 d-wave 配对机制（争议：AFM-QCP 还是价键涨落？）

1986：重费米子 + 非常规超导的黄金十年开始
  UPt₃ 发现多重超导相（A/B/C），暗示二维奇宇称表示 [来源待验证，综述引用]
  更重要：Bednorz-Müller 发现 La₂₋ₓBaₓCuO₄（铜氧化物）→ 全领域注意力转向铜氧化物

1998：Mathur et al.（Cambridge，UK）
  CeIn₃ 在压力下：AFM 磁序 TN 被抑制至零，SC 穹在 QCP 附近出现
  [Mathur et al. 1998, Nature 394, 39]（确定）
  ★ 教科书式的"压力调控 QCP 诱导超导"：
    - 最干净的 QCP→SC 实验证据
    - 排除了声子机制（纯金属，Tc 只有 ~0.2K，极低）
    - 但这个 Tc ≈ 0.2K 极低，表明 QCP 驱动本身效率不高

2001：Petrovic et al.（Los Alamos，USA）
  发现 CeCoIn₅，Tc = 2.3K
  [Petrovic et al. 2001, JPCM 13, L337]（确定）
  ★ 迄今 Ce 基重费米子 Tc 最高，d-wave 配对证据最强的材料
  - 热导率测量确认线节点（d-wave 特征）[来源待验证，Izawa 2001 系列]
  - QPI 测量与 d-wave 一致 [观察]
  - FFLO 态候选（在高场 + 低温区有异常相变迹象）[观察，来源待核查]

2019：Ran et al.（Maryland，USA）
  发现 UTe₂，Tc = 1.65K
  [Ran et al. 2019, Science 365, 684]（确定）
  ★ 当前重费米子研究最大热点：
    - 多重超导相（B-T 相图复杂，H_c2 极大各向异性）
    - Knight shift 测量最初暗示 triplet（spin susceptibility 不降低）
    - 但 Sr₂RuO₄ 教训提醒：Knight shift 数据可能误导
    - TSC（拓扑超导）候选，但实验证据远未充分 [观察]
```

---

## 3. 主要材料详析

### 3.1 CeCu₂Si₂：首个重费米子超导体，两个 SC 穹

**[历史确定；微观机制 [猜想]]**

```
基本参数（[Steglich 1979 PRL 43, 1892]（确定））：
  Tc ≈ 0.6K（ambient pressure，样品质量敏感！）
  晶体结构：ThCr₂Si₂ 型（I4/mmm）
  有效质量：m* ≈ 200–400 m_e（比热系数 γ ~ 700 mJ/mol·K²）[来源待验证]
  配对对称性：d-wave [猜想，无节点测量或 QPI 直接确认]

  两个超导穹（[观察，压力实验发现]）：
    SC1（低压穹）：
      存在于 AFM 磁序附近（TN ~ 0.8K 可被压力抑制）
      被认为由 AFM-QCP 涨落驱动 [猜想，Mathur/Steglich 学派]
      节点结构：可能有线节点（d-wave 暗示），但直接实验证据弱 [观察]
    SC2（高压穹，P ~ 4–5 GPa）：
      存在于价键涨落（valence fluctuation）区域
      机制：Ce³⁺ ↔ Ce⁴⁺ 价键涨落介导的配对
      [Holmes 2004, JPCM（来源待精确核查）；Ito 2021 系列（来源待核查）]
      SC1 与 SC2 的配对对称性可能不同！（争议）[猜想]
  
  ⚠️ 反谄媚：CeCu₂Si₂ 的 d-wave 标签比 CeCoIn₅ 弱得多（没有热导率节点的直接测量）。"AFM-QCP 驱动 d-wave"在 CeCu₂Si₂ 中仍是推测。
```

### 3.2 UPt₃：多相图，最强 f-wave 候选

**[观察 — 实验现象确定；对称性指认 [猜想]]**

```
基本参数：
  Tc ≈ 0.53K（ambient pressure）[来源待验证，综述引用]
  晶体结构：MgCd₃ 型六方（P6₃/mmc）
  有效质量：m* ~ 几十至 ~200 m_e（γ ~ 420 mJ/mol·K²）[来源待验证]

多重超导相（[定理 — 实验已确认三相存在]）：
  H-T 相图中存在 A、B、C 三个超导相，由两个 Tc 转变分开：
    Tc1 ≈ 0.53K（A/B 相边界）
    Tc2 ≈ 0.48K（A/B 相分裂）
    高场相：C 相（仅在特定场方向出现）[来源待核查]
  [Taillefer & Lonzarich 1988 series（来源待精确核查）]

  A/B 相分裂的意义（[猜想]）：
    两个 Tc 暗示：配对涉及多维不可约表示（非一维，不能单 Tc 分裂）
    B 相：自发 TRS 破缺（µSR 测量到内磁场 ~ 0.5 Gauss）[来源待验证]
    主流指认：E₂u 表示（f-wave，spin triplet）[Choi & Sauls 1991（来源待核查）]
    → 若 E₂u 正确，则 UPt₃ 是 f-wave 的最强实验候选
    → 但 35 年后争议仍未决（E₁u 也有支持者）[猜想]

  ⚠️ 核心反谄媚：UPt₃ 的 f-wave E₂u 是重要猜想，不是确认结论。没有实验技术能直接测量 ℓ=3 的 f-wave 节点（热导率角向测量极为困难）。Tc ≈ 0.53K 极低，极少实验组有能力研究。
```

### 3.3 CeCoIn₅：d-wave 最确认的重费米子超导体

**[d-wave 配对为 [猜想] 中证据最强的重费米子材料]**

```
基本参数：
  Tc = 2.3K（ambient pressure）[Petrovic et al. 2001, JPCM 13, L337]（确定）
  晶体结构：HoCoGa₅ 型（P4/mmm），四方层状
  有效质量：m*/m_e ≈ 70–90 [来源待验证，综述引用]
  上临界场：H_c2∥c ≈ 12T，H_c2⊥c ≈ 5T [Petrovic 2001]（来源待核查精确值）
  AFM 关联：CeCoIn₅ 本身不磁有序，但极接近 AFM QCP（施压 → AFM）[观察]

d-wave 配对的实验证据（CeCoIn₅ 是重费米子中证据最完整的）：
  (1) 热导率角向测量（[猜想，最强单一证据]）：
      κ(θ) 在 H ∥ ab 旋转时出现 4 倍对称振荡 → 线节点与 d_{x²-y²} 一致
      [Izawa et al. 2001 PRL 87, 057002（来源待精确核查）]
  (2) 低温比热 C(T) ~ T² 行为 → 线节点（d-wave 或 f-wave）[观察，多组测量]
  (3) ¹¹⁵In NMR：1/T₁T ~ 一定温度行为与节点态一致 [观察，来源待核查]
  (4) QPI（准粒子干涉）：与 d_{x²-y²} 节点方向一致 [观察，Akbari 2011 等（来源待核查）]
  
  综合评估：CeCoIn₅ d-wave 是重费米子中最被接受的配对指认，但仍是 [猜想]（缺乏 ARPES 相位测量或 Josephson 结磁通量量子化的直接判决实验）

FFLO 态候选（[观察，争议中]）：
  高场低温区（H ≈ 10–12T，T < 0.7K）：比热/磁化率有奇异相变 [观察]
  部分解释：FFLO（Fulde-Ferrell-Larkin-Ovchinnikov）有限动量配对态
  问题：STM 空间成像未见明确的 FFLO 条纹 [观察，2026 状态]
  结论：FFLO 是吸引人的解释但未确认 [猜想]

  ⚠️ 反谄媚：CeCoIn₅ 是最好的重费米子，但"最好"只是相对于其他重费米子。与铜氧化物相比：Tc = 2.3K vs 铜氧化物 ~100K；d-wave 证据：铜氧化物（Tsuei-Kirtley Josephson 结确认）>> CeCoIn₅（热导率暗示）。二者在配对证据质量上差距很大。
```

### 3.4 URhGe / UCoGe：铁磁超导体，再入超导

**[定理 — 共存确认；机制 [猜想]]**

```
URhGe 基本参数：
  T_Curie（FM）≈ 9.5K，Tc（SC）≈ 0.25K（ambient pressure）[来源待验证]
  FM + SC 共存（体积效应，非界面）[定理，µSR 验证]
  配对：triplet（FM 背景下 singlet Cooper 对破坏，triplet 可共存）[猜想]

UCoGe 基本参数：
  T_Curie（FM）≈ 2.5K，Tc（SC）≈ 0.6K（ambient pressure）[来源待验证]
  FM 自发磁化极小（M ~ 0.03 μ_B/U），与 URhGe 相比"弱铁磁"

再入超导（Re-entrant SC in URhGe，[观察，最显著特征]）：
  H ∥ b 方向（硬轴）在 H ~ 12T 处出现第二超导区域！
  物理机制 [猜想，Lévy et al. 2005（来源待精确核查）]：
    12T 处存在磁矩重取向（spin reorientation）
    重取向附近，横向 FM 自旋涨落增强 → 增强 triplet 配对
    → 高场 SC 区域反而比低场 Tc 更高（异常！）
  这是 B4（FM 涨落机制）的**最直接实验体系**，没有之一

与 B4 MECE 的关联：
  URhGe/UCoGe 是"FM 涨落驱动 triplet SC"假说的最干净实验体
  排除了 AFM 机制（材料本身就是 FM）
  排除了声子机制（SC 在 FM 背景下，Tc 极低）
  → 剩余最合理解释：FM 自旋涨落介导 triplet Cooper 对 [猜想]
  
  ⚠️ 反谄媚：URhGe 和 UCoGe 的 Tc 极低（0.25K 和 0.6K），实验极为困难（需要 mK 级稀释制冷）。"最直接实验体系"是说机制最干净，不是说实验容易或结论确定。
```

### 3.5 UTe₂：当前最热点，triplet + TSC 候选

**[观察 — 实验现象丰富；但每个解释都存在严重争议；Sr₂RuO₄ 教训必须时刻铭记]**

```
基本参数：
  Tc = 1.65K（ambient pressure）[Ran et al. 2019, Science 365, 684]（确定）
  晶体结构：斜方（Immm），准一维 U 链沿 a 轴
  不是铁磁体：磁化率 Curie-Weiss 行为，T*～16K（FM 涨落，但无长程序）[来源待核查]
  H_c2：极大且强各向异性：H_c2∥a >> 30T（帕利极限）[来源待核查]
    Pauli 极限违反本身暗示 triplet（singlet 对被 Zeeman 劈裂破坏）[观察]

实验上的"exciting"特征（逐条诚实评估）：
  (1) Pauli 极限违反：
      H_c2∥a >> H_p（Pauli 极限）→ 暗示 triplet [观察]
      ⚠️ 但：Pauli 极限也可以被自旋-轨道耦合效应（singlet NCS 系统）违反
  
  (2) Knight shift 不降低（[观察，但有 Sr₂RuO₄ 教训！]）：
      早期 ¹²⁵Te NMR：超导态 Knight shift 保持（暗示 triplet，spin ↑↑ 对）
      ⚠️ Sr₂RuO₄ 的教训：这类 Knight shift 测量可能被涡旋对流、样品加热误导
      ⚠️ 更好的测量（冷却优化）或其他方法才能确认
      结论：[猜想，证据质量比 Sr₂RuO₄ 最初"确认"差不多，应保持同等级别怀疑]
  
  (3) 多重超导相（[定理 — 相变存在；解释 [猜想]）：
      B-T 相图中至少 2-3 个超导相（SC1/SC2/SC3）[来源待核查，2021-2023 年系列]
      高压下 Tc 可达 3–4K（比 ambient 更高）[来源待核查]
      类比 UPt₃ 多重相 → 可能涉及多维表示
  
  (4) 手性表面态（[观察，争议]）：
      扫描隧道谱（STS）在某些样品表面看到手性 Andreev 弧 [来源待核查，2021]
      若确认 = TSC（拓扑超导），会有 Majorana 表面态
      ⚠️ 但：表面态对样品质量、氧化、终止面极敏感。"手性弧"的解读争议很大。
  
  (5) 可能的 TRSB（TRS 破缺）：
      部分µSR 数据暗示零场内磁场 [来源待核查]
      ⚠️ µSR 对磁杂质极为敏感，U 基材料本身容易有磁杂质

综合评估（反谄媚核心）：
  UTe₂ 是重要的研究体系，但所有"exciting"特征都处于 [观察→猜想] 层级。
  没有一个特征达到 Sr₂RuO₄ 最初"确认"的水平（而 Sr₂RuO₄ 后来翻案了）。
  "UTe₂ 是 triplet TSC" = [猜想，证据尚不充分]
  应对标准：达到铜氧化物 d-wave（Tsuei-Kirtley 相位测量）的确认水平才算结论。
```

---

## 4. Doniach 相图详解

### 4.1 两个竞争能量尺度的数学结构

**[定理 — Doniach 1977 Physica B；细节是 [猜想]]**

```
完整的 Doniach 相图分析：

基本能量尺度：
  T_RKKY：Ce/U 格点磁矩之间通过传导电子的间接耦合
    LaTeX: T_{RKKY} \sim J_K^2 N(E_F)
    ASCII: T_RKKY ~ J_K^2 * N(EF)
    依赖：J_K 的二次方（二阶微扰）→ J_K 小时 T_RKKY 也小但衰减慢
    空间依赖：RKKY 振荡，R_ij^{-3} cos(2k_F R_ij) → 可以是 AFM 或 FM 耦合
  
  T_Kondo：单格点 Kondo 屏蔽温度
    LaTeX: T_K \sim W \exp\!\left(-\frac{1}{J_K N(E_F)}\right)
    ASCII: T_K ~ W * exp(-1 / (J_K * N(EF)))
    依赖：J_K 增大 → T_K 指数增长（远比 T_RKKY 增长快）

相图的四个区域：
  区域 I（小 J_K）：T_RKKY >> T_K
    → 长程磁序（AFM 或 FM）
    → 局域磁矩为主，传导电子弱耦合
    → 此区域：Kondo 单杂质效应但无相干屏蔽

  区域 II（中等 J_K）：T_RKKY ~ T_K
    → QCP！（两个尺度竞争，量子涨落最强）
    → 非 FL 行为（ρ ~ AT^α，α ≠ 2；C/T ~ -log T 等）
    → SC dome 通常出现在此区域附近（若其他条件满足）

  区域 III（大 J_K）：T_K >> T_RKKY
    → 重费米液体（Kondo 相干屏蔽 + Fermi 液体恢复）
    → γ 大，A 大，但磁矩已被屏蔽，无磁序
    → 一般不出现 SC（无磁涨落来驱动）

  区域 IV（压力/掺杂调控的跨越）：
    化学压力（等价于 |J_K| 增大）可以推动体系从区域 I → II → III
    这是为什么 CeIn₃、CeCu₂Si₂ 在压力下在 QCP 附近出现 SC

最干净的 QCP→SC 例子（CeIn₃）：
  常压：AFM，TN ≈ 10K
  压力增大：TN 连续降低
  P ≈ 2.5GPa：TN → 0，QCP！
  SC 穹：P ≈ 2–3GPa，Tc ≈ 0.2K（极低）
  [Mathur et al. 1998, Nature 394, 39]（确定）
  ⚠️ 注意：Tc = 0.2K 非常低，QCP 驱动的 SC 并不"高效"
```

### 4.2 非 FL 量子临界行为

**[观察 — 非 FL 行为实验广泛确认；理论解释争议大]**

```
QCP 附近的非 Fermi 液体行为（[观察，实验确认；理论 [猜想]]）：

  电阻率：
    普通 FL：ρ ~ ρ_0 + AT²
    QCP 附近重费米子：ρ ~ ρ_0 + AT^α，α < 2（常见 α = 1 或 α = 3/2）
    CeCoIn₅（近 QCP）：ρ ~ T（线性！Strange metal 行为）[观察，多组测量]
    这个 T 线性同时也是铜氧化物 Strange metal（A8 MECE）的特征！

  比热：
    FL：C/T = γ（常数）
    QCP 附近：C/T ~ γ - A√T 或 C/T ~ -log(T)（对数发散或幂律）
    YbRh₂Si₂（AFM-QCP）：C/T ~ -log(T) 超过两个数量级 [来源待核查]

  磁化率：
    FL：χ ~ const
    QCP 附近：χ ~ T^{-α}（幂律发散）

  解释框架的分歧（[猜想]）：
    Hertz-Moriya-Millis：用有效场论处理 AFM 序参数涨落，Gaussian + 量子修正
    → 预测 3D-AFM QCP：C/T ~ T^{1/2}（幂律），与部分实验符合
    局域量子临界理论（Qimiao Si 等）：f 电子 Kondo 本身在 QCP 处崩溃（"Kondo breakdown"）
    → 预测不同幂律，与 YbRh₂Si₂ 某些数据更符合
    → 两个理论框架均有部分支持，均有反例，未有决定性判决 [猜想]
```

---

## 5. 重费米子 vs 铜氧化物对比

**[观察层级对比表]**

```
重费米子超导体 vs 铜氧化物超导体：对比表

  | 性质               | 重费米子                      | 铜氧化物                        |
  |--------------------|------------------------------|---------------------------------|
  | 主要轨道           | 4f（Ce）/ 5f（U）            | 3d（Cu）                        |
  | 有效质量 m*        | 100–1000 m_e                 | ~3–5 m_e（轻，但关联强）        |
  | Tc 最高值          | ~2.3K（CeCoIn₅）             | ~134K（Hg-1223，常压）          |
  | 实用价值           | ❌ 无（极低温）               | 部分实用（液氮温区 YBCO）        |
  | 主要配对           | d-wave（Ce 基）              | d_{x²-y²}-wave（最确认）        |
  | 配对确认程度       | [猜想]（热导率暗示）          | [定理级]（Josephson/ARPES/QPI）  |
  | U 基配对           | triplet（猜想！）             | N/A                             |
  | QCP 调控           | 最干净（压力/化学压力）       | 存在但复杂（掺杂同时改变多参数） |
  | 可调性             | 高（压力、替换 CoIn₅ 中元素） | 中（掺杂，但 Tc 对杂质敏感）    |
  | Strange metal      | 出现在 QCP 附近（CeCoIn₅）   | 最优掺杂附近宽泛区域             |
  | 母体磁态           | AFM（Ce 基）或 FM（U 基）     | AFM 绝缘体（Mott 绝缘体）        |
  | Mott 物理相关性    | 弱（局域 f 但传导带金属）     | 强（Cu 3d 在半满时是 Mott 绝缘体）|
  | 实验可及性         | 极难（mK 级，敏感样品质量）   | 中等（液氮→液氦，多种技术）      |
  | 理论成熟度         | 低（Kondo + QCP + 配对三重挑战）| 中（RVB/AFM 涨落大量研究）      |
```

---

## 6. 关键定量数据

**[严格标注来源；区分确定/待核查]**

```
主要材料参数汇总：

CeCu₂Si₂：
  Tc ≈ 0.6K（ambient pressure）[Steglich et al. 1979, PRL 43, 1892]（确定）
  比热系数 γ ~ 700 mJ/(mol·K²) [来源待验证，综述引用]
  有效质量 m*/m_e ~ 200–400 [来源待验证]
  AFM 转变 TN ≈ 0.8K（化学计量比偏离时）[来源待核查]

CeCoIn₅：
  Tc = 2.3K（ambient pressure）[Petrovic et al. 2001, JPCM 13, L337]（确定）
  H_c2∥c ≈ 12T（T→0）[来源待验证，Petrovic 2001 或后续测量]
  m*/m_e ≈ 70–90 [来源待验证，综述引用]
  比热系数 γ ~ 300–400 mJ/(mol·K²) [来源待验证]

UPt₃：
  Tc ≈ 0.53K（上转变温度）[来源待验证，综述引用]
  Tc ≈ 0.48K（下转变温度）[来源待验证]
  比热系数 γ ~ 420 mJ/(mol·K²) [来源待验证]

URhGe：
  Tc（SC）≈ 0.25K [来源待验证]
  T_Curie（FM）≈ 9.5K [来源待验证]

UCoGe：
  Tc（SC）≈ 0.6K [来源待验证]
  T_Curie（FM）≈ 2.5K [来源待验证]
  再入 SC 场：H ≈ 12T（∥b 轴）[来源待验证，Lévy 2005 系列]

UTe₂：
  Tc = 1.65K [Ran et al. 2019, Science 365, 684]（确定）
  H_c2∥a > 30T（T→0，超过 Pauli 极限）[来源待核查，2019-2021 测量]
  多重超导相（至少 SC1/SC2）[来源待核查]

CeIn₃（QCP 教科书体系）：
  TN（AFM，ambient）≈ 10K [来源待核查]
  QCP 压力 ≈ 2.5GPa [Mathur 1998]（确定，从 Nature 394 数字读出）
  Tc（SC，at QCP）≈ 0.2K [Mathur et al. 1998, Nature 394, 39]（确定）

⚠️ 注意：以上大量参数标注 [来源待验证]。这不是"找不到来源"，而是遵守数据诚实规则：这些数值来自综述记忆而非原始论文核查。任何需要精确数值的分析必须回溯原始文献。
```

---

## 7. 关键反谄媚

**[核心立场 — 对重费米子超导常见过度解读的纠正]**

```
反谄媚 1：Tc 极低，完全没有任何实际应用价值

  ✅ 事实：CeCoIn₅ Tc = 2.3K（迄今 Ce 基最高）；实用超导需要 ≥ 77K（液氮）
  ❌ 夸大：有人说重费米子是"理解非常规超导的钥匙"，因此有间接价值
  ✅ 诚实版本：这个体系是优秀的理论实验室（QCP 干净，可调参数少），
              但从 2.3K 到 77K 没有已知路径。研究价值 = 机制理解，不是应用。
  ⚠️ 结论：如果你的目标是室温超导，重费米子是错误的出发点。

反谄媚 2：QCP 驱动超导是猜想，不是定理

  ✅ 有证据支持：CeIn₃（Mathur 1998）SC dome 正好在 QCP 附近 → 关联很强
  ❌ 夸大："QCP 驱动超导机制已经确立"
  ✅ 诚实版本：关联不等于因果。SC dome 出现在 QCP 附近，
              但配对媒介是 AFM 涨落（HMM）还是 Kondo 本身崩溃的临界模式，
              还是其他机制，没有判决性实验。
  层级标注：QCP→SC 关联是 [观察]，AFM 涨落媒介是 [猜想]

反谄媚 3：UTe₂ ≠ 确认的 triplet 超导，Sr₂RuO₄ 教训！

  背景：Sr₂RuO₄ 被"确认"为 triplet p-wave 超导长达 24 年（1994-2019），
        主要证据之一是 Knight shift 不降低。
        2019-2020 年：更精确的测量发现 Knight shift 其实降低了——翻案！
  
  UTe₂  的问题：
    Knight shift 证据：初期测量与 Sr₂RuO₄ 翻案前同等质量
    Pauli 极限违反：可以有 singlet + SOC 解释
    多重超导相：存在但不能直接确认 triplet
    手性表面态 STS：样品质量和解读有争议
  
  ✅ 结论：UTe₂ triplet 标签是 [猜想，中等证据强度]，
            远未到可以声称"确认"的水平。
  ⚠️ 警告：即使现有证据都是真实的，Sr₂RuO₄ 教训告诉我们：
            似乎一致的多个证据可以同时被一个更精确实验推翻。

反谄媚 4：大量数值来源待验证，不可直接引用

  本文档中大量数值标注 [来源待验证]：
    - CeCu₂Si₂：γ, m*, TN 来自综述记忆
    - UPt₃：Tc1/Tc2，γ 来自综述记忆
    - URhGe/UCoGe：Tc, T_Curie 来自综述记忆
  
  ✅ 要求：用于论文引用的任何数值必须回溯原始文献，获取 DOI 确认。
  ✅ 本文档功能：提供框架和关键参考文献起点，不是可以直接引用的来源。

反谄媚 5：f-wave（UPt₃）和 triplet（UTe₂）的实验基础远弱于 d-wave（铜氧化物）

  铜氧化物 d-wave：[定理级]（Josephson 结相位测量，Tsuei-Kirtley 1994，无歧义）
  CeCoIn₅ d-wave：[猜想]（热导率节点，可信但非相位测量）
  UPt₃ f-wave E₂u：[猜想]（多相图间接推论，35 年未决）
  UTe₂ triplet：[猜想]（Knight shift + Pauli 极限，均有替代解释）
  
  → f-wave 和 triplet 重费米子中的配对对称性是超导领域中**实验基础最薄弱的重要课题之一**。
```

---

## 8. 与 Paper A（Allen-Dynes 多通道框架）的关联

**[完全不适用：非声子，极端有效质量]**

```
Paper A 核心：Two-Channel Allen-Dynes（声子 + 电子-电子通道的多声子框架扩展）

重费米子与 Paper A 的关系：
  (1) 配对媒介不是声子：
      重费米子的非常规配对由磁涨落（AFM 或 FM）介导 [猜想]
      Allen-Dynes 框架基于电子-声子作用 → 完全不适用
  
  (2) 极端有效质量问题：
      Allen-Dynes 公式 Tc ~ ω_log × exp(-1/(λ-μ*)) 中
      λ 定义为声子耦合常数，与 m* 的关系复杂
      对 m* ~ 100-1000 m_e 的体系：传统 BCS/Allen-Dynes 框架中
      大 λ 预期大 Tc，但重费米子 Tc 极低 → 反向矛盾
      原因：重费米子的"大 γ"来自准粒子带宽窄化（带宽重整化），
            不是由电声耦合 λ 增大带来的。这两种 m* 增大机制完全不同！
  
  (3) 总结：
      Paper A 的多通道框架不适用于重费米子体系
      两者的联系：重费米子可以作为"反例"—— 有极大 m*（γ 极大），但 Tc 极低
      这正好说明：BCS/Allen-Dynes 框架中"大 m* → 大 DOS → 大 λ → 高 Tc"
      的逻辑链在 Kondo 重整化机制下断裂 → 机制完全不同
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026）| 主要障碍 | 相关 MECE |
|------|----------------|---------|-----------|
| **UTe₂ 配对对称性（triplet or not？）** | [猜想，争议激烈] | 需要相位灵敏实验（Josephson/ARPES 极难）| C5, C9 |
| **CeCoIn₅ FFLO 态确认** | [观察]，未经 STM 空间成像确认 | 极低温 + 高场 STM 技术要求极高 | C8 |
| **UPt₃ E₂u vs E₁u** | 35 年未决，[猜想] | f-wave 节点无法用现有热导率/ARPES 技术直接测量 | C6 |
| **QCP 驱动 SC 的量子临界机制** | [猜想，两框架并存：HMM vs local QCP]| 缺乏判决性实验 | B3, B4 |
| **重费米子 Tc > 5K 是否可能？** | [猜想，否定倾向] | QCP 附近涨落机制本身 Tc 效率低，无新体系突破 | B3 |
| **f 电子拓扑超导（f-TSC）** | 初始理论预测 + UTe₂ 候选，[猜想] | 直接观测 Majorana 在 mK 温度下极难 | F4, F5 |
| **Kondo 晶格超导的统一理论** | 不存在。各家框架部分适用 | Kondo + 磁序 + 配对三个强关联效应无可靠多体方法 | B14 |
| **UTe₂ 多重超导相的起源** | [观察，分类困难] | 相变标定在 mK + T 需要极低噪声 | C7 |

---

## 附录：核心速查（ASCII 格式，适配 Discord）

```
=== D8 重费米子超导体 核心速查 ===

[1] 五大代表材料（全部 Tc < 5K！）：
  CeCu₂Si₂：Tc ≈ 0.6K [Steglich 1979 PRL 43, 1892] ✅（首个，d-wave 猜想）
  CeCoIn₅：Tc = 2.3K [Petrovic 2001 JPCM 13, L337] ✅（d-wave 最强，FFLO 候选）
  UPt₃：Tc ≈ 0.53K [来源待验证]（f-wave E₂u 35 年争议，多相 A/B/C）
  UTe₂：Tc = 1.65K [Ran 2019 Science 365, 684] ✅（triplet 候选，⚠️ 争议大！）
  URhGe：Tc ≈ 0.25K [来源待验证]（FM+SC 共存，再入超导在 ~12T）

[2] 物理核心：Doniach 相图
  T_RKKY ~ J_K^2 * N(EF)（磁序）
  T_K ~ exp(-1/(J_K*N(EF)))（Kondo 屏蔽）
  QCP：T_RKKY ~ T_K 处，TN→0，SC dome 在此附近
  最干净例子：CeIn₃（Mathur 1998 Nature 394, 39）✅

[3] 有效质量：
  m*/m_e ~ 100–1000（最重的量子准粒子）[来源待验证]
  CeCoIn₅：m*/m_e ≈ 70–90 [来源待验证]
  比热系数 γ ~ 100–1000 mJ/(mol·K²)（vs 普通金属 1–10）

[4] 配对对称性（层级严格）：
  CeCoIn₅：d-wave [猜想，热导率节点证据，非相位测量]
  UTe₂：triplet [猜想，Sr₂RuO₄ 教训级别警告！]
  UPt₃：f-wave E₂u [猜想，35 年未决]
  QCP→d-wave：[猜想，HMM 框架，非确认机制]

=== 核心反谄媚 ===
  ⚠️ Tc 全部 < 5K，完全无实用价值。研究价值 = 机制理解，不是应用。
  ⚠️ "QCP 驱动 SC" = [猜想]，关联 ≠ 因果机制
  ⚠️ UTe₂ triplet ≠ 确认。Sr₂RuO₄ 24 年翻案教训必须铭记！
  ⚠️ 大量数值 [来源待验证]，不可直接引用，需回溯原始文献
  ⚠️ Paper A（Allen-Dynes 声子）完全不适用于重费米子体系

=== D8 与 MECE 关联图 ===
  B3（AFM 涨落）→ D8 CeCu₂Si₂/CeCoIn₅ d-wave 的驱动来源
  B4（FM 涨落）→ D8 URhGe/UCoGe triplet，再入超导（B4 最干净实验体系）
  B10（Hund's）→ D8 Kondo 屏蔽 = Hund J_H + 反铁磁 J_K 竞争的 f 电子实现
  B14（Mottness）→ D8 Kondo 晶格是 f 电子的 Mott 物理极端形式
  C3（d-wave）→ D8 CeCoIn₅ d_x²-y²，AFM-QCP 框架与铜氧化物类比
  C5（p-wave）→ D8 UTe₂ triplet 候选，Sr₂RuO₄ 教训的直接关联
  C6（f-wave）→ D8 UPt₃ E₂u 候选，实验基础最薄弱的重要体系
  C9（Singlet/Triplet）→ D8 包含两类：Ce 基（singlet）+ U 基（triplet 猜想）
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**字节大小估计：** ~16 KB

**反谄媚审计：**
- ✅ Tc 极低（< 5K）明确声明无实用价值，并给出与铜氧化物的具体对比
- ✅ UTe₂ triplet 标注 [猜想]，Sr₂RuO₄ 24 年翻案教训明确引用
- ✅ QCP 驱动 SC 机制标注 [猜想]，关联≠因果的逻辑明确说明
- ✅ UPt₃ f-wave E₂u 标注 [猜想]，35 年未决明确记录
- ✅ 大量数值标注 [来源待验证]，区分 Steglich 1979/Mathur 1998/Petrovic 2001/Ran 2019（确定）与综述记忆（待核查）
- ✅ Paper A 完全不适用的原因给出具体物理分析（非声子机制，Kondo 重整化 ≠ 大 λ）
- ✅ 配对对称性的确认程度分级（铜氧化物 d-wave 定理级 >> CeCoIn₅ 猜想 >> UTe₂/UPt₃ 争议猜想）
- ✅ HMM vs 局域 QCP 两个理论框架均列出，未偏向其中一个
- ✅ Sr₂RuO₄ 教训在 UTe₂ 节专门引用，警告等级与 C5 文档一致
- ✅ PREDICTION vs RETRODICTION：所有"机制支持"均标注为 [猜想]，无"已预测后验证"的虚假升格

**D 部分状态：** D1 ✅ → D2 ✅ → D3 ✅ → D4 ✅ → D5 ✅ → D6 ✅ → D7 ✅ → **D8 ✅（当前）**
