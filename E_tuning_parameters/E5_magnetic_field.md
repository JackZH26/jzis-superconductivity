# E5. 磁场（Magnetic Field）— 轨道效应、Pauli 极限与 FFLO 态

**MECE 编号：** E5
**关联 MECE：**
- A6（临界场 — Hc₁/Hc₂/Hc₃ 现象学；本文物理机制补充 A6 的实验现象）
- A7（临界电流 — 涡旋运动 Lorentz 力 → 临界电流；轨道效应产生涡旋）
- C8（PDW — FFLO 是磁场诱导的有限动量配对；PDW 是 FFLO 零场自发版本 [猜想]）
- C5（p-wave — triplet 不受 Zeeman 拆配；Pauli 极限不适用）
- D8（重费米子 — CeCoIn₅ FFLO 候选；URhGe 再入 SC；D8 是磁场极端行为的主战场）
- D11（2D/界面 — Ising SOC；NbSe₂/MoS₂ 面内 Hc₂ >> H_P；Pauli 极限大幅违反）
- D13（2D 半导体 SC — MoS₂ Ising SC；面内磁场 Hc₂ 超越 Pauli 极限）

**层级关系：** E5 是**外部磁场**对超导体的综合效应。磁场是超导最主要的"敌人"（Meissner 效应排斥磁通；过高磁场摧毁超导），但在某些特殊体系（磁性重费米子、自旋三重态超导体、Ising SOC 体系）中，磁场也可以是超导的"触发器"（再入 SC）或对 Pauli 极限的豁免使高场超导成为可能。E5 与 A6（临界场现象学）互补：A6 给实验数据，E5 给机理。
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（轨道效应 / Pauli 极限 / FFLO / 再入 SC；反幻觉规则严格执行；[来源待验证] 大量标注）

---

## 1. 物理定义与核心思想

### 1.1 两大破坏机制（[定理，GL 和 BCS 框架严格推导]）

磁场对超导的破坏通过两条独立物理路径实现：

```
=== 机制一：轨道效应（Orbital Depairing）[定理，GL 理论] ===

物理图像：
  外加磁场 H → 超导体内部磁通量子 Φ₀ 进入 → 涡旋（Abrikosov 涡旋）形成
  每个涡旋携带磁通量子：
    Φ₀ = h / (2e) = 2.0678 × 10⁻¹⁵ Wb（来源确定，基本常数）
  超过 Hc₂ → 涡旋核（正常态）填满整个样品 → 超导消失

GL 理论上临界场 [定理]：
  LaTeX: \mu_0 H_{c2}^{orb} = \frac{\Phi_0}{2\pi\xi^2}
  ASCII: mu_0 * Hc2_orb = Phi_0 / (2 * pi * xi^2)

  其中：
    xi   = GL 相干长度（Ginzburg-Landau coherence length）
    Phi_0 = h/(2e) = 磁通量子

相干长度温度依赖（BCS 干净极限，T → T_c）[定理]：
  LaTeX: \xi(T) = \xi_0 / \sqrt{1 - T/T_c}
  ASCII: xi(T) = xi_0 / sqrt(1 - T/Tc)
  → T → 0 时 xi(T) → xi_0（BCS 相干长度）
  → T → Tc 时 xi → ∞，Hc₂ → 0（相变点）

逆直觉结论：
  "更干净"的样品（散射更少）→ 更大的 xi_0（更长相干长度）
  → 更小的 Hc₂（轨道）！
  → 干净极限反而被轨道效应更容易破坏

=== 机制二：Pauli 顺磁效应（Zeeman Depairing）[定理，BCS 框架] ===

物理图像：
  外加磁场 H → Zeeman 劈裂 ΔE = g μ_B H
  → ↑ 自旋电子费米面上移：E_F + ΔE
  → ↓ 自旋电子费米面下移：E_F - ΔE
  → 当 ΔE ~ Δ（超导能隙），Cooper 对 (k↑, -k↓) 能量不对等 → 配对不再稳定

Chandrasekhar-Clogston（CC）极限 [定理，1962-1963]：
  LaTeX: \mu_0 H_P = \frac{\Delta_0}{\sqrt{2} \mu_B} \approx 1.84 T_c \text{ (T/K)}
  ASCII: mu_0 * H_P = Delta_0 / (sqrt(2) * mu_B) ≈ 1.84 * Tc (T/K)

  其中：
    Delta_0 = BCS 零温能隙 = 1.764 k_B T_c
    mu_B    = 玻尔磁子 = 9.274 × 10⁻²⁴ J/T
    H_P     = Pauli 极限（Chandrasekhar-Clogston 极限）

  数值示例：
    Tc = 1K  → mu_0 * H_P ≈ 1.84 T
    Tc = 10K → mu_0 * H_P ≈ 18.4 T
    Tc = 92K → mu_0 * H_P ≈ 169 T

  关键约束：仅对 singlet Cooper 对有效！
  triplet 配对（C5/C6）：两电子自旋平行 → 不受 Zeeman 拆散 → 无 Pauli 极限

=== 哪个先破坏超导？Maki 参数 ===

比较两个临界场大小 [定理，Maki 1966]：

  Maki 参数（参数化 Pauli 效应相对强度）：
    LaTeX: \alpha = \frac{\sqrt{2} H_{c2}^{orb}}{H_P}
    ASCII: alpha = sqrt(2) * Hc2_orb / H_P

  解读：
    alpha << 1：Hc₂(orb) << H_P → 轨道效应主导；超导被轨道破坏
    alpha >> 1：Hc₂(orb) >> H_P → Pauli 效应主导；Pauli 极限成为实际 Hc₂
    alpha ~ 1：两种机制共同决定 Hc₂

  典型体系（[来源待验证，方向性正确]）：
    铝（Al）：xi₀ ~ 1600 nm，alpha << 1（轨道主导）
    铌（Nb）：xi₀ ~ 40 nm，alpha ~ 中等
    重费米子（CeCoIn₅）：xi₀ ~ 数 nm（强关联缩短 xi），alpha >> 1（Pauli 主导）
```

### 1.2 Meissner 效应：磁通完全排斥（第 I 类超导体）

```
第 I 类（Type-I）超导体 [定理]：
  H < Hc → Meissner 效应：完全抗磁性（B = 0 体内）
  H > Hc → 突然进入正常态（不是 Abrikosov 涡旋态）
  GL 参数 kappa = lambda / xi < 1/sqrt(2)

第 II 类（Type-II）超导体 [定理]：
  H < Hc₁ → 完全 Meissner 态（排斥所有磁通）
  Hc₁ < H < Hc₂ → 混合态（Abrikosov 涡旋格子 + 超导基体共存）
  H > Hc₂ → 完全正常态
  GL 参数 kappa = lambda / xi > 1/sqrt(2)
  → 大多数实用超导体、铜氧化物、铁基、重费米子均为 II 型
```

---

## 2. 历史关键节点

```
★★★ 1957 Abrikosov（诺贝尔奖 2003）— II 型超导体与磁通涡旋格子理论

  来源：A.A. Abrikosov, Zh. Eksp. Teor. Fiz. 32, 1442 (1957)（来源确定）
  贡献：
    → GL 理论中 kappa > 1/sqrt(2) → II 型超导存在混合态（Vortex State）
    → Abrikosov 涡旋格子：磁通量子 Φ₀ 以三角格子排列
    → Hc₁（第一个 Φ₀ 进入）和 Hc₂（完全正常态）的 GL 理论预言
  意义：超导物理的里程碑；解释了为什么高场超导（NbTi, Nb₃Sn）可以存在

★★ 1962-1963 Chandrasekhar & Clogston — Pauli 顺磁极限推导 [定理]

  来源：
    B.S. Chandrasekhar, Appl. Phys. Lett. 1, 7 (1962)（来源确定）
    A.M. Clogston, Phys. Rev. Lett. 9, 266 (1962)（来源确定）
  贡献：推导出 mu_0 H_P = 1.84 Tc (T/K)
  意义：建立了 singlet SC 的磁场上限（Pauli 极限）

★★ 1964 Fulde-Ferrell / Larkin-Ovchinnikov — FFLO 态理论预言

  来源：
    P. Fulde & R.A. Ferrell, Phys. Rev. 135, A550 (1964)（来源确定）
    A.I. Larkin & Yu.N. Ovchinnikov, Zh. Eksp. Teor. Fiz. 47, 1136 (1964)（来源确定）
  贡献：预言在 Pauli 极限附近超导可以以有限动量配对存在（FFLO 态）
  现状：60 年过去，FFLO 实验证实仍存争议 [观察，2026]

★★ 1966 Maki — Maki 参数与轨道+Pauli 综合理论

  来源：K. Maki, Phys. Rev. 148, 362 (1966)（来源确定）
  贡献：引入 Maki 参数 alpha；统一处理轨道和 Pauli 两种 depairing 机制

★★ 1980s-1990s — 重费米子超导中高场研究

  多组工作（[来源待验证，综述级认知]）：
    CeRu₂Si₂、CeCu₂Si₂、UPt₃ 等 → 低 Tc 但极强 Pauli 效应（重费米子 xi₀ 短）
    → 磁场下超导相图高度丰富，多相共存
  意义：建立重费米子作为 Pauli 极限和 FFLO 研究主战场的认识

★★★ 2001-2005 CeCoIn₅ — FFLO 态最强候选

  来源：C. Petrovic et al., J. Phys.: Condens. Matter 13, L337 (2001)（发现，来源确定）
         A. Bianchi et al., Phys. Rev. Lett. 91, 187004 (2003)（FFLO 候选，来源待核查具体内容）
  体系：CeCoIn₅，Tc ≈ 2.3K，Hc₂ ≈ 12T (H∥c)
  关键：Hc₂ >> H_P(理论) ≈ 4.2T → 强 Pauli 极限违反
         高场低温区（H ≈ 9-11T, T < 0.5K）比热出现额外跳变 → FFLO 候选相变
  ⚠️ 争议：STM 空间成像未确认 FFLO 周期性条纹 [观察，截至 2026]

★★★ 2005 Lévy et al. — URhGe 再入超导（场诱导 SC）

  来源：N. Lévy et al., Phys. Rev. Lett. 95, 257601 (2005)（来源待核查具体数据）
  体系：URhGe（U 基重费米子铁磁 SC）
  结果：b 轴磁场 H ≈ 12T 附近 → SC 再入（Tc 随场升高而升高）
  机制：FM 涨落在 Hc(b) ~ 12T 处增强 → triplet 配对增强 → SC 恢复 [来源待验证]

★★★ 2016 Xi et al. / Saito et al. — Ising SC（MoS₂/NbSe₂）

  来源：
    X. Xi et al., Nat. Phys. 12, 139 (2016)（来源确定，NbSe₂ Ising SC）
    Y. Saito et al., Nat. Phys. 12, 144 (2016)（来源确定，MoS₂ Ising SC）
  结果：单层 NbSe₂/MoS₂ 面内 Hc₂ >> H_P（Pauli 极限大幅违反）
  机制：面外 Ising SOC → 自旋锁定 → 面内磁场不能有效 Zeeman 拆散 singlet Cooper 对
  意义：证明 Pauli 极限违反无需 triplet 配对（Ising SOC 是另一路径）

★★ 2020s — 高场脉冲磁体 + 二维超导体系统研究

  多组工作（[来源待验证]）：
    各向异性 Hc₂ 系统测量 → 费米面各向异性 + SOC 效应分离
    高场 NMR/μSR → FFLO 候选体系的空间成像
  技术进步：混合磁体（NHMFL 45T DC）+ 脉冲磁场（> 60T）
  意义：扩展了实验可探索的磁场范围，开始系统挑战 FFLO 鉴定难题
```

---

## 3. 三个临界场：Hc₁ / Hc₂ / Hc₃

**[II 型超导体；[定理] 均来自 GL 理论或 Saint-James-de Gennes 理论]**

```
=== Hc₁（下临界场）：磁通开始进入 ===

物理含义：第一个磁通量子 Φ₀ 进入超导体，形成第一个 Abrikosov 涡旋

公式 [定理，GL 理论，kappa >> 1 极限]：
  LaTeX: \mu_0 H_{c1} \approx \frac{\Phi_0}{4\pi\lambda^2} \ln(\kappa)
  ASCII: mu_0 * Hc1 ≈ (Phi_0 / (4*pi*lambda^2)) * ln(lambda/xi)

  其中：
    lambda = London 磁场穿透深度
    xi     = GL 相干长度
    kappa  = lambda/xi（GL 参数）

实际意义：
  Hc₁ 通常很小（对铜氧化物：mu_0 Hc₁ ~ 10-100 mT）[来源待验证]
  → 实用超导体几乎总处于混合态（Vortex State）
  → "迈斯纳悬浮"实验看到的 Meissner 态是 H < Hc₁ 的极低场效应

=== Hc₂（上临界场）：超导完全消失 ===

公式 [定理，GL 理论]：
  LaTeX: \mu_0 H_{c2} = \frac{\Phi_0}{2\pi\xi^2}
  ASCII: mu_0 * Hc2 = Phi_0 / (2 * pi * xi^2)

温度依赖（线性外推）[定理，GL 理论近 Tc]：
  LaTeX: \mu_0 H_{c2}(T) \approx \mu_0 H_{c2}(0) \cdot \left(1 - \frac{T}{T_c}\right)
  ASCII: mu_0 * Hc2(T) ≈ mu_0 * Hc2(0) * (1 - T/Tc)

WHH 理论（脏极限 Pauli 效应修正）[定理，Werthamer-Helfand-Hohenberg 1966]：
  考虑 Pauli 效应后，Hc₂(0) 比纯轨道值低：
  LaTeX: \mu_0 H_{c2}(0) \approx -0.69 T_c \left.\frac{d(\mu_0 H_{c2})}{dT}\right|_{T_c}
  ASCII: mu_0 * Hc2(0) ≈ 0.69 * |d(mu_0*Hc2)/dT|_Tc * Tc（轨道极限）
  Pauli 效应将此值进一步压低（alpha 参数决定压低程度）

实用场合典型值（[来源待验证，方向性数量级正确]）：
  Nb（元素金属）：mu_0 Hc₂ ≈ 0.2 T（低 Tc = 9.3K）
  NbTi（合金）：mu_0 Hc₂ ≈ 15 T（Tc ≈ 9K，短 xi）
  Nb₃Sn（A15）：mu_0 Hc₂ ≈ 29 T（Tc ≈ 18K）
  YBCO（铜氧化物）：mu_0 Hc₂(H⊥ab) ≈ 120-250 T（极短 xi，ab 面内）[来源待验证]
  CeCoIn₅（重费米子）：mu_0 Hc₂ ≈ 12T (H∥c)，≈ 5T (H∥ab) [来源待验证]

=== Hc₃（第三临界场：表面超导）===

物理含义：H > Hc₂ 后，体材已正常，但样品表面仍维持超导（薄层 ~ xi 厚度）

Saint-James–de Gennes 理论 [定理，1963]：
  LaTeX: H_{c3} \approx 1.695 \, H_{c2}
  ASCII: Hc3 ≈ 1.695 * Hc2

  条件：磁场垂直样品表面时
  物理：表面破坏了超导序参量的边界条件 → 比体内允许更高的临界场

  面内（平行）磁场的 Hc₃：
    Hc₃(平行) >> 1.695 Hc₂（显著增大）
    薄膜 + 平行场 → 表面超导可以在极高场下存活 [来源待验证]

  应用意义：
    用于区分表面 SC 和体 SC
    纳米线、薄膜的高场实验中需考虑 Hc₃ 效应
```

---

## 4. FFLO 态（Fulde-Ferrell-Larkin-Ovchinnikov）

**[高磁场下有限动量配对；60 年理论预言，实验确认仍有争议]**

```
=== FFLO 态形成条件 [定理，FF 1964 / LO 1964] ===

前提：singlet SC + 强 Pauli 效应（alpha >> 1）+ 干净体系（散射少）

机制：
  外磁场 H → Zeeman 劈裂 → ↑↓ 自旋费米面移位量 δk = g μ_B H / ħ v_F
  当 δk > 1/xi₀（配对相干区间外）→ 普通 BCS (k↑, -k↓) 配对不稳定
  
  FFLO 解：形成有限质心动量 Q 的 Cooper 对：
    (k + Q/2, ↑) 和 (-k + Q/2, ↓)，使得两电子能量相等

空间序参量 [定理，FF vs LO 不同构型]：
  Fulde-Ferrell：
    LaTeX: \Delta(\mathbf{r}) = \Delta_0 e^{i\mathbf{Q}\cdot\mathbf{r}}
    ASCII: Delta(r) = Delta_0 * exp(i*Q*r)
    → 行波：|Delta(r)| = const，但相位螺旋

  Larkin-Ovchinnikov：
    LaTeX: \Delta(\mathbf{r}) = \Delta_0 \cos(\mathbf{Q}\cdot\mathbf{r})
    ASCII: Delta(r) = Delta_0 * cos(Q * r)
    → 驻波：序参量周期性节面（空间节线）
    → 能量更低，更可能实现 [猜想，数值模拟]

FFLO 波矢大小（BCS 估算）[定理，近 Pauli 极限处]：
  LaTeX: |\mathbf{Q}| \approx \frac{2 g \mu_B H}{\hbar v_F}
  ASCII: |Q| ≈ 2 * g * mu_B * H / (hbar * v_F)

  典型值（CeCoIn₅）：|Q| 对应实空间周期 ~ 数十 nm [来源待验证]

=== 实验判据（寻找 FFLO 的实验标志）===

  判据 1：Hc₂ > H_P（Pauli 极限违反）— 必要但不充分
    → 其他机制（Ising SOC, triplet）也可以超越 Pauli 极限

  判据 2：比热在高场低温区出现额外异常（相变痕迹）— 充分性待定
    → CeCoIn₅：H ~ 9-11T 处有额外比热跳变 [Bianchi 2003，来源待核查]
    → 可能是 FFLO 相变，但也可能是磁场诱导的涡旋结构变化 [争议]

  判据 3：μSR 磁场分布不均匀（LO 节面 → 局部正常态）— 强判据
    → 尚无确认 CeCoIn₅ FFLO 条纹的 μSR 结果 [来源待验证，2026]

  判据 4（最强）：STM 空间成像 → 直接看到 LO 序参量节面周期
    → CeCoIn₅ STM 研究：未见报道的 FFLO 条纹成像 [观察，2026]
    → 技术挑战：CeCoIn₅ 解理面质量差；需要 > 10T + 极低温 + 高分辨 STM

  判据 5：NMR 线型 → LO 态中局部正常区的 Knight shift 变化
    → 有部分 NMR 证据，但争议 [来源待验证]

=== CeCoIn₅：FFLO 最强候选 [来源待验证，具体数值待核查] ===

  参数：Tc ≈ 2.3K，d-wave 配对，mu_0 Hc₂ ≈ 12T (H∥c)
  Pauli 极限估算：mu_0 H_P = 1.84 * 2.3 ≈ 4.2 T → Hc₂ ≈ 2.9 * H_P → 强 Pauli 违反
  Maki 参数估算：alpha ≈ 3–4（Pauli 主导体系）[来源待验证]
  
  FFLO 候选相（"Q 相"）：
    H ≈ 9-11T，T < 0.5K（0.2 Tc 量级）区域内有额外相变迹象
    比热、热导率等热力学测量见异常 [来源待验证，多篇 2003-2007 文章]
  
  ⚠️ 关键反谄媚：
    60 年后 FFLO 仍未有直接实空间确认（STM 成像缺失）
    CeCoIn₅ 高场相的物理可能更复杂（涡旋结构变化？CDW？）

=== 与 C8（PDW）的关联 ===

  FFLO：磁场诱导的有限动量配对（外场 → Q ≠ 0 自发形成）
  PDW（Pair Density Wave）：零场下自发形成的有限动量配对（不需要磁场）
  
  [猜想]：PDW 是 FFLO 的"零场自发版本"——相同的有限动量配对机制，
          不同的诱发外因（场 vs 内禀强关联）
  [定理]：两者的序参量形式相同：Delta(r) = Delta_Q exp(iQ·r) [数学上等价]
  ⚠️ 物理上是否真正等价仍有争议 [观察，截至 2026]
```

---

## 5. Pauli 极限违反的多种机制

**[关键反谄媚：Pauli 极限违反 ≠ triplet 配对！有多种独立机制]**

```
=== 机制一：Triplet 配对（C5/C6）===

原理 [定理]：
  triplet Cooper 对：两电子自旋平行（自旋态 |↑↑⟩ 或 |↓↓⟩ 或 |↑↓+↓↑⟩）
  → 磁场 Zeeman 拆散仅影响 singlet（|↑↓-↓↑⟩ 态）
  → triplet 对的两电子均感受相同 Zeeman 移位 → 能量差为零 → 不受 Pauli 拆散

  后果：
    triplet SC 无 Pauli 极限（Hc₂ 可以任意高，仅受轨道效应限制）
    面内 g 因子 → 平行磁场对 Sz = 0 triplet 有部分拆散，但弱于 singlet

  典型体系：
    UTe₂：triplet SC 候选，mu_0 Hc₂ ~ 35T（远超 Pauli 极限）[来源待验证，D8]
    URhGe：triplet + 再入 SC [来源待验证，D8]
    Sr₂RuO₄：长期争议配对态（2020 后 singlet 倾向增加）[来源待验证，D8/C5]

=== 机制二：Ising SOC（D11/D13）— 最重要的"非 triplet 路径" ===

原理 [定理，群论 + DFT 推导]：
  2D 体系 + 面外 Ising 型 SOC（保持 C₃v 或 C₂v 对称性）
  → 电子自旋被面外方向钉扎（Ising anisotropy）
  → 面内磁场 H∥ 的 Zeeman 效应被强 SOC 抑制（有效 g 因子大幅减小）
  → 面内 Hc₂ 大幅超越 Pauli 极限（仍是 singlet 配对！）

  严格表述：
    轨道效应仍决定面外 Hc₂（H ⊥ 面内）
    Ising SOC 使面内 Hc₂ >> 轨道极限（2D 薄膜平行场时轨道效应本已弱）
    → 综合结果：面内 H∥c₂ >> H_P（Chandrasekhar-Clogston 极限）

  典型体系（确认数据）：
    NbSe₂ 单层（面内 Hc₂）：
      [Xi et al., Nat. Phys. 12, 139 (2016)]（来源确定）
      面内 Hc₂ >> H_P（具体倍数 [来源待验证，核查原文数据]）
    
    MoS₂/ionic-gated（面内 Hc₂）：
      [Saito et al., Nat. Phys. 12, 144 (2016)]（来源确定）
      面内 Hc₂ 超越 Pauli 极限约 4 倍 [来源待验证，核查原文具体值]

  ⚠️ 核心反谄媚（最重要！）：
    Ising SC 是 singlet 配对超越 Pauli 极限！
    不需要 triplet，不需要 FFLO
    → 面内 Hc₂ >> H_P 不能单独作为 triplet 配对的证据

=== 机制三：Rashba SOC（E4 相关）===

原理 [定理，群论推导]：
  界面/非中心对称体系中的 Rashba SOC → 混合 singlet-triplet 配对
  → 有效降低 Zeeman 拆散效率 → Hc₂ 高于纯 singlet 预测值

  效果：修正 Pauli 极限（介于纯 singlet 和纯 triplet 之间）
  典型体系：非中心对称超导体（CePt₃Si 等）[来源待验证，D8]

=== 机制四：g 因子重整化（重费米子）===

原理 [猜想，重费米子强关联效应]：
  重费米子 → 电子有效质量 m* >> m_e
  → 朗道费米液体重整化 → 有效 g 因子 g* ≠ 2（可大可小）
  → 若 g* < 2 → 有效 Zeeman 劈裂减小 → Pauli 极限升高
  
  ⚠️ 这是 [猜想]，具体体系 g* 值需实验测定 [来源待验证]

=== 四种机制对比 ===

  机制             配对类型    是否改变配对    需要哪种对称性
  ─────────────────────────────────────────────────────────
  Triplet 配对     triplet     是（本质上）    TR 破缺 + SOC
  Ising SOC        singlet     否！            2D + C₃v/C₂v + 面外 SOC
  Rashba SOC       混合        部分           界面/非中心
  g* 重整化        singlet     否              重费米子强关联

  → Pauli 极限违反的实验观测，必须排除上述 singlet 路径，才能支持 triplet 配对
```

---

## 6. 再入超导与场诱导超导

```
=== 再入超导（Re-entrant SC）===

定义：
  标准流程：SC（低场）→ 正常态（中场）→ SC 再次出现（高场）
  关键：高场下 Tc 随场升高而升高（反常！）

机制（[猜想，具体体系中证明强度不同]）：
  高场改变磁序涨落谱 → 对 triplet 配对有利的涨落增强 → SC 重现
  
  URhGe 机制（FM 涨落增强 triplet SC）：
    URhGe 是铁磁超导体（FM + SC 共存）
    外加 b 轴磁场 → 近 H ~ 12T 处：FM 涨落剧烈增强（场增强的 FM 软化）
    → triplet 配对相互作用增强 → 原本已被场抑制的 SC 重新出现
    → SC 窗口在 H ≈ 8-13T 附近（再入 SC 区间）[来源待验证，Lévy 2005 等]

  典型体系：
    URhGe：b 轴 H ≈ 8-13T → 再入 SC（Tc_reentrant ~ 0.4K）[来源待验证，Lévy 2005]
    UCoGe：c 轴磁场 → 类似再入行为 [来源待验证]

=== 场诱导超导（Field-induced SC）===

定义：
  标准流程：正常态（零场/低场）→ SC 只在强磁场下出现
  区别于再入 SC：从未有过低场 SC 相

典型例子：
  BETS₂FeCl₄（有机超导体）：
    Jaccarino-Peter 效应 [来源待验证]：
    正常磁性离子（Fe³⁺）产生内禀交换场 H_ex（方向可调）
    外加磁场 H_ext 补偿 H_ex → 有效场 H_eff = H_ext - H_ex ≈ 0
    → "消磁"效应 → SC 在场中重现
    [来源待验证：BETS₂FeCl₄ ~ 1998-2001 日本组实验]

  Eu-La₃Ni₂O₇（[来源待验证，Yang 2026 相关]）：
    Eu 替代 → 磁性增强 → 磁场诱导 SC 出现 [来源待验证]

  URhGe 也可以看作场诱导 SC（高场 SC 从未有过低场版本）[来源待验证]

=== 再入 SC vs 场诱导 SC 对比 ===

  类型            零场状态    SC 的场范围           关键机制
  ──────────────────────────────────────────────────────────
  再入 SC         SC 相存在   先失超导，后恢复       FM 涨落增强 / 配对涨落
  场诱导 SC       正常态      只在强场下超导          Jaccarino-Peter / 磁性抑制消除
  标准 SC         SC 相存在   场摧毁，不恢复          轨道 + Pauli 破坏
```

---

## 7. 关键定量数据

**[反幻觉：无确认来源一律 [来源待验证]；数字仅供量级参考]**

```
=== 确认定理数据（有具体来源） ===

Chandrasekhar-Clogston 极限 [定理，来源确定]：
  mu_0 * H_P (T) = 1.84 * Tc (K)
  → Tc=1K → H_P ≈ 1.84 T
  → Tc=10K → H_P ≈ 18.4 T
  → Tc=92K（YBCO）→ H_P ≈ 169 T

磁通量子 [基本常数，来源确定]：
  Phi_0 = h/(2e) = 2.0678 × 10⁻¹⁵ Wb = 2067.8 T·nm²

Abrikosov 涡旋格子：[Abrikosov, Sov. Phys. JETP 5, 1174 (1957)，来源确定]
FFLO 理论预言：[Fulde & Ferrell, PR 135, A550 (1964)；LO 1964，来源确定]
CC 极限：[Chandrasekhar 1962；Clogston 1962，来源确定]

Ising SC（面内 Hc₂ >> H_P）：
  NbSe₂ 单层：[Xi et al., Nat. Phys. 12, 139 (2016)，来源确定]
  MoS₂ ionic-gated：[Saito et al., Nat. Phys. 12, 144 (2016)，来源确定]

=== 待验证数据（[来源待验证]）===

CeCoIn₅（重费米子 d-wave SC）：
  Tc ≈ 2.3K
  mu_0 Hc₂ ≈ 12T (H∥c)，≈ 5T (H∥ab)
  H_P(理论) ≈ 1.84 * 2.3 ≈ 4.2 T → Hc₂/H_P ≈ 2.9（Pauli 极限大幅违反）
  FFLO 候选区：H ≈ 9-11T，T < 0.5K
  [Petrovic 2001（发现，来源确定）；其余数值来源待验证]

URhGe（铁磁超导体，triplet SC 候选）：
  Tc₀ ≈ 0.25K（零场低温 SC）[来源待验证]
  再入 SC 场窗：H_b ≈ 8-13T（近 b 轴磁场）[来源待验证，Lévy 2005]
  再入 SC Tc_max ≈ 0.4K（高于零场值）[来源待验证]

UTe₂（强 triplet SC 候选）：
  Tc ≈ 1.6-2K（依样品质量）[来源待验证]
  面内 mu_0 Hc₂ ~ 35T（面 a/b），远超 H_P ≈ 3T [来源待验证]
  → 最强 Pauli 极限违反案例之一

YBCO（铜氧化物）：
  Tc = 92K，H_P(理论) ≈ 169T
  mu_0 Hc₂ (H⊥CuO₂) ≈ 100-250T（极高，需脉冲磁场测量）[来源待验证]
  → 实际 Hc₂ 被轨道效应限制，Pauli 效应不是主要限制

MoS₂ 单层（Ising SC）：
  面内 mu_0 Hc₂ ≈ 50T [来源待验证，核查 Saito 2016 原文具体数值]
  H_P(理论，Tc~6K) ≈ 11T → Hc₂/H_P ≈ 4.5（面内）[来源待验证]

=== 关键公式汇总（ASCII 格式） ===

[1] GL 上临界场 [定理]：
  mu_0 * Hc2_orb = Phi_0 / (2 * pi * xi^2)
  = h/(2e) / (2 * pi * xi^2)

[2] Chandrasekhar-Clogston Pauli 极限 [定理]：
  mu_0 * H_P = Delta_0 / (sqrt(2) * mu_B)
             ≈ 1.84 * Tc (T/K)

[3] Maki 参数 [定理]：
  alpha = sqrt(2) * Hc2_orb / H_P

[4] GL 下临界场（kappa >> 1）[定理]：
  mu_0 * Hc1 ≈ (Phi_0 / (4*pi*lambda^2)) * ln(lambda/xi)

[5] Saint-James–de Gennes 第三临界场 [定理]：
  Hc3 ≈ 1.695 * Hc2（垂直场情况）

[6] FFLO 序参量波矢（BCS 估算，近 Pauli 极限）[定理]：
  |Q| ≈ 2 * g * mu_B * H / (hbar * v_F)
```

---

## 8. 关键反谄媚

```
⚠️ 反谄媚 1（最重要）：Pauli 极限违反 ≠ triplet 配对

  常见误判：
    实验：面内 Hc₂ >> H_P
    错误结论：因为超越 Pauli 极限，所以是 triplet SC

  正确逻辑：
    面内 Hc₂ >> H_P 的可能原因：
    (a) Ising SOC（singlet SC + 面外 SOC 锁定自旋）→ 见 NbSe₂/MoS₂ 确认案例
    (b) Triplet 配对（自旋平行 → 不受 Zeeman 拆散）
    (c) Rashba SOC（singlet-triplet 混合 → 修正 Pauli 极限）
    (d) g 因子重整化（重费米子）
    
    → Pauli 极限违反是必要条件，但远不够支持 triplet 结论
    → 需要额外探针：NMR Knight shift 测量（singlet: KS 下降；triplet: KS 不变）

⚠️ 反谄媚 2：FFLO 在 CeCoIn₅ 的证据不充分

  已有证据（不充分）：
    ✅ Hc₂ >> H_P（Pauli 违反，alpha >> 1）
    ✅ 高场低温区比热出现额外跳变（相变信号）
    ✅ 热导率各向异性随场变化
  
  缺失的关键证据：
    ❌ STM 空间成像未见 LO 周期性节面条纹
    ❌ μSR 空间不均匀性的确认
    ❌ NMR 线型中 LO 局部正常区的直接证据
  
  替代解释：
    高场相可能是涡旋结构相变（Abrikosov → Josephson 涡旋格子）
    可能是磁有序 + 超导 vortex 相互作用改变
  
  → 结论：CeCoIn₅ 的高场相是 FFLO 的最佳候选，但尚未确认

⚠️ 反谄媚 3：高场实验的技术限制带来系统误差

  DC 磁场极限：
    超导磁体最高 ~ 20T（实用）
    混合磁体（NHMFL 等）最高 45T（连续 DC）[来源待验证]
    → 许多重费米子 Hc₂ > 20T，需要脉冲磁场
  
  脉冲磁场问题：
    脉冲磁体 ~ 60-100T 可达（毫秒量级）[来源待验证]
    样品焦耳加热 → 有效温度高于标称值 → 系统误差
    脉冲时间短 → 动态效应、驰豫效应
  
  → "高场 Hc₂ 测量"在脉冲场中的数据需谨慎解读

⚠️ 反谄媚 4：Hc₂ 各向异性的物理来源多元

  各向异性 Hc₂（H∥ >> H⊥）的可能来源：
  (a) 费米面各向异性（二维性强 → 面内 Hc₂ 高）
  (b) 面外轨道效应弱（2D 薄膜平行场时涡旋核受限）
  (c) Ising SOC（仅增强面内 Hc₂）
  (d) 配对对称性各向异性（d-wave 节点方向 vs 反节点方向 Hc₂ 不同）
  
  → 各向异性 Hc₂ 不能直接推断配对对称性各向异性
  → 需要联合 ARPES（费米面各向异性）+ NMR（配对对称性）+ STM 联合判断

⚠️ 反谄媚 5：再入 SC 的磁性涨落增强机制是 [猜想]

  URhGe 再入 SC 的机制：
    FM 涨落在 H ≈ 12T 增强 → triplet 配对增强 [猜想]
    理由：
      ✅ 再入 SC 窗口确实在磁化率异常（FM 涨落增强区）出现 [来源待验证]
      ❌ FM 涨落强度的定量计算未能准确预言 SC Tc 提升幅度 [来源待验证]
    
    替代机制（[猜想]）：
      高场改变费米面拓扑（Lifshitz 相变）→ 新的嵌套条件 → SC 增强
      → 与 FM 涨落机制难以直接区分

⚠️ 反谄媚 6：CC 极限 1.84 Tc 是干净 singlet BCS 的严格结果，多体修正会改变它

  CC 极限推导假设：
    ✅ BCS 弱耦合（Eliashberg 强耦合修正会改变数字）
    ✅ 无 SOC
    ✅ 各向同性能隙
    ✅ 干净（无杂质，无散射）
  
  实际修正：
    强耦合（大 lambda）：数字修正（1.84 → 略大或小）[定理，Eliashberg]
    节点能隙（d-wave 等）：节点处 Δ=0 → 节点附近 Pauli 效应增强 → 实际 H_P 降低 [猜想]
    杂质散射：散射混合 singlet + triplet → 复杂 [猜想]
  
  → 用 1.84 Tc 做精确计算需谨慎，方向性可靠，数字有 ~20% 不确定度
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026-04） | 主要障碍 | 相关 MECE |
|------|-------------------|---------|-----------|
| **CeCoIn₅ 的高场相是否真是 FFLO 态？** | 热力学证据存在，空间成像缺失 | 极低温（< 0.3K）+ 高场（> 10T）+ 高分辨 STM | D8, C8, E5 |
| **UTe₂ 的多相超导图（H-T 相图）** | 多个 SC 相存在，机制不清 [来源待验证] | 样品质量差；多相图复杂 | D8, C5, E5 |
| **高场下铜氧化物的 Hc₂（> 100T）** | 脉冲场数据有限，争议 [来源待验证] | 脉冲场系统误差；YBCO 临界场极高 | D3, A6, E5 |
| **Ising SC 中 Hc₂ 的精确定量理论** | 定性理解清楚，定量仍有偏差 [猜想] | 多轨道 + SOC + 涨落的全精确计算 | D11, D13, E5 |
| **URhGe 再入 SC 的精确机制** | FM 涨落 vs Lifshitz 相变争议 | 高压 + 高场 + 低温 联合测量 | D8, B4, E5 |
| **场诱导 SC（Eu-LNO 等）的普适性** | 个别体系报道，系统性不足 [来源待验证] | 材料单晶制备困难 | D5, G3, E5 |
| **FFLO 的零场类比（PDW）与 FFLO 的关系** | 理论关联提出，实验缺失 [猜想] | PDW 直接空间成像技术限制 | C8, E5 |
| **脉冲高场（> 60T）+ 极低温（< 0.1K）技术** | 技术开发中 [来源待验证] | 脉冲场 + 稀释制冷机兼容性 | 全体 E5 相关 |

---

## 附录：核心速查（ASCII 格式）

```
=== E5 磁场 核心速查 ===

[1] 两大破坏机制 [定理]：

  轨道效应（Orbital Depairing）：
    磁通涡旋 → Hc₂_orb = Phi_0 / (2*pi*xi^2)
    "干净"材料（大 xi）→ 小 Hc₂（逆直觉！）

  Pauli 效应（Zeeman Depairing，仅 singlet）：
    CC 极限：mu_0 * H_P ≈ 1.84 * Tc (T/K)
    triplet SC：无 Pauli 极限

  Maki 参数：alpha = sqrt(2) * Hc₂_orb / H_P
    alpha >> 1 → Pauli 主导（重费米子典型）
    alpha << 1 → 轨道主导（干净 BCS 典型）

[2] 三个临界场 [定理]：
  Hc₁：mu_0 * Hc1 ≈ (Phi_0/(4*pi*lambda^2)) * ln(lambda/xi)（第一涡旋进入）
  Hc₂：mu_0 * Hc2 = Phi_0 / (2*pi*xi^2)（超导消失）
  Hc₃：Hc3 ≈ 1.695 * Hc2（表面超导）

[3] FFLO 态 [定理（预言）/ 观察（实验未确认）]：
  条件：singlet SC + alpha >> 1 + 干净体系
  序参量：Delta(r) = Delta_0 * cos(Q*r)（LO 态）
  最强候选：CeCoIn₅（热力学证据，STM 直接成像缺失）

[4] Pauli 极限违反机制：
  triplet → 无 Pauli 极限（配对类型改变）
  Ising SOC → singlet 仍超越 H_P（面内磁场 + 2D 体系）← 最重要非 triplet 路径
  Rashba SOC → 混合 singlet-triplet → 修正 H_P
  g* 重整化 → 修正 Zeeman 劈裂（重费米子）

[5] 关键反谄媚（最高优先级）：
  ⚠️ 面内 Hc₂ >> H_P ≠ triplet 配对！
     Ising SOC 也能实现 singlet 超越 Pauli 极限
  ⚠️ FFLO 在 CeCoIn₅：热力学证据存在，STM/μSR 空间成像未确认
  ⚠️ 高场脉冲磁体实验 → 样品加热 → 系统误差
  ⚠️ CC 极限 1.84 Tc → BCS + 无 SOC + 各向同性假设；强耦合/节点/杂质会修正

[6] 确认数据（文献确认）：
  Phi_0 = h/(2e) = 2.0678 × 10⁻¹⁵ Wb（基本常数）
  CC 极限：mu_0 H_P ≈ 1.84 Tc（T/K）[Chandrasekhar 1962; Clogston 1962]
  Abrikosov 涡旋格子 [Abrikosov, JETP 1957]
  Ising SC（NbSe₂）：[Xi et al., Nat. Phys. 12, 139 (2016)]
  Ising SC（MoS₂）：[Saito et al., Nat. Phys. 12, 144 (2016)]
  CeCoIn₅ 发现：[Petrovic et al., J. Phys.: Condens. Matter 13, L337 (2001)]

[7] 待验证数据（[来源待验证]）：
  CeCoIn₅：mu_0 Hc₂ ≈ 12T (H∥c)，H_P ≈ 4.2T，FFLO 候选区 H≈9-11T T<0.5K
  URhGe：再入 SC 场窗 H_b ≈ 8-13T，Tc_reentrant ≈ 0.4K [Lévy 2005]
  UTe₂：面内 mu_0 Hc₂ ~ 35T（远超 H_P ≈ 3T）
  MoS₂ 单层：面内 Hc₂ ≈ 50T（H_P ≈ 11T → 约 4.5 倍违反）

[8] MECE 关联图：
  E5 → A6（临界场现象学：E5 提供机理，A6 提供实验现象）
  E5 → A7（临界电流：涡旋运动 Lorentz 力 → 临界电流）
  E5 → C8（PDW：FFLO 是场诱导版；PDW 是零场自发版）
  E5 → C5（p-wave triplet：不受 Pauli 极限约束）
  E5 → D8（重费米子：FFLO 主战场；再入 SC；UTe₂/CeCoIn₅/URhGe）
  E5 → D11（2D/界面：Ising SC；面内 Hc₂ >> H_P；singlet 超越 Pauli 极限）
  E5 → D13（2D 半导体 SC：MoS₂ Ising SC；Saito/Xi 2016）

[9] 层级分类汇总：
  [定理]：CC 极限 1.84 Tc；GL Hc₂ 公式；Hc₁ 公式；Hc₃ = 1.695 Hc₂；FFLO 理论预言
  [猜想]：URhGe 再入 SC 的 FM 涨落机制；PDW 与 FFLO 物理等价性；
           CeCoIn₅ 高场相为 FFLO；UTe₂ 纯 triplet 配对
  [观察]：CeCoIn₅ 高场相的热力学异常（存在，2003-2007）；
           FFLO 空间成像缺失（截至 2026）；高场脉冲测量的技术系统误差

[10] 物理直觉速查：
  大 xi → 小 Hc₂（逆直觉：干净材料反而对轨道效应脆弱）
  小 xi（重费米子）→ 大 Hc₂（轨道）→ Pauli 效应变得重要 → FFLO 可能
  2D + Ising SOC → 面内磁场不能有效 Zeeman 拆散 → 面内 Hc₂ >> H_P（singlet！）
  triplet → 无论什么磁场方向，Pauli 极限无效
  FM 涨落 + 强场 → 可能再入 SC（triplet 体系）
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**字节大小估计：** ~13.5 KB

**反谄媚审计：**
- ✅ Pauli 极限违反 ≠ triplet：全文核心主题，第 5 节系统阐述，第 8 节反谄媚 1 强调
- ✅ FFLO 在 CeCoIn₅ 未确认：第 4 节明确列出缺失的关键证据（STM/μSR），第 8 节反谄媚 2
- ✅ 高场脉冲实验系统误差：第 8 节反谄媚 3
- ✅ Hc₂ 各向异性来源多元：第 8 节反谄媚 4
- ✅ URhGe 再入 SC 机制为猜想：第 6 节、第 8 节反谄媚 5
- ✅ CC 极限 1.84Tc 的适用条件：第 8 节反谄媚 6
- ✅ 所有实验数值标注 [来源待验证]；确认数据明确标注来源
- ✅ 层级标注：[定理]/[猜想]/[观察] 全文覆盖
- ✅ 未解问题 8 条，含空间成像、脉冲高场技术等前沿方向

**E 部分状态：** **E1 ✅ E2 ✅ E3 ✅ E4 ✅ E5 ✅（2026-04-28，v1.0）** E 部分覆盖率 70% → 80% 🎉
