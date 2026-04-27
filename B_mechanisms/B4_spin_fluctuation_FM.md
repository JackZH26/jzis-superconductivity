# B4. 自旋涨落介导（FM）— 铁磁自旋涨落配对（spin-triplet）

**MECE 编号：** B4
**关联 MECE：** B3（AFM 涨落对比）、C5/C6/C7（p/f/chiral 波）、C9（singlet vs triplet）、A6（Pauli limit 违反）、G2（SC + FM 共存）、G3-G4（field-induced/re-entrant）、G7（spin-triplet）、D5（Eu-nickelate）、D8（重费米子 UTe₂/URhGe/UCoGe/UGe₂）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Berk-Schrieffer 1966 + Fay-Appel 1980 + Aoki-Flouquet 2019 综述 + Yang 2026）

---

## 1. 物理定义与核心思想

**自旋涨落介导超导（FM 通道）：** 电子通过交换**铁磁**（FM）自旋涨落形成 Cooper 对。这是 B3（AFM）的"镜像兄弟"，但配对结构截然不同。

[关键对比]

| 通道 | q-空间增强 | 配对函数对称性 | 自旋态 |
|------|----------|--------------|-------|
| **B3 AFM** | q ≈ Q（反铁磁波矢）| **反号** Δ(k+Q) = -Δ(k) | spin-singlet（d 波）|
| **B4 FM** | q ≈ 0 | **同号** Δ(k) ≈ Δ(k+q≈0) | **spin-triplet**（p 波）|

**[物理图像]** FM 涨落使两个电子的自旋平行能量更低 → Pauli 不相容要求轨道部分**反对称**（odd parity）→ 自然给出 p 波（l=1, m=0,±1）或 f 波（l=3）。

> **关键** spin-triplet SC 自动**规避 Pauli limit**（自旋分量不被 Zeeman 能破坏）→ 这是 A6 中 UTe₂、URhGe、Eu-nickelate 高场存活的根本物理原因。

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| **1966** | **Berk-Schrieffer** 首次讨论 spin-fluctuation 配对（含 FM 通道）| PRL 17, 433 |
| 1972 | Anderson-Brinkman-Morel ³He B 相 spin-triplet | RMP 47, 415 |
| **1980** | **Fay-Appel** FM SC 理论 | PRB 22, 3173 |
| **2000** | **Saxena et al.** UGe₂ 在压力下发现 SC（FM + SC 共存）| Nature 406, 587 |
| 2001 | **Aoki et al.** URhGe SC（铁磁体）| Nature 413, 613 |
| 2003 | Huy et al. UCoGe SC | PRL 99, 067006 |
| **2005** | **Lévy et al.** URhGe field-induced re-entrant SC | Science 309, 1343 |
| 2017 | UTe₂ SC 发现，争议起 | Ran 2019 Science 365, 684 |
| 2019 | **Aoki-Knebel-Flouquet** 重费米子 FM SC 综述 | J. Phys. Soc. Jpn. 88, 022001 |
| 2019 | **Pustogow et al.** Sr₂RuO₄ 修正为 d 波（推翻 p+ip）| Nature 574, 72 |
| **2026** | **Yang et al.** Eu-nickelate field re-entrant SC at 45 T | arXiv:2508.14666（已精读）|

---

## 3. 数学框架

### 3.1 FM 涨落的 RPA 极化率

[定义] FM 涨落的关键判据：χ_s(q ≈ 0, 0) 大且接近发散：
$$\chi_s(0, 0) = \frac{\chi_0(0)}{1 - U \chi_0(0)}$$

当 1 - U χ₀(0) → 0 时 FM 不稳定性发生（Stoner 判据）。

### 3.2 配对核（与 AFM 对比）

[定义] FM 通道配对相互作用（spin-triplet 部分）：
$$V_{\text{pair}}^{(t)}(\mathbf{k}, \mathbf{k}') = -\frac{1}{2} U^2 \chi_s(\mathbf{k} - \mathbf{k}', 0)$$

[关键差异]
- AFM 通道（B3）系数 +3/2（V > 0，需反号配对）
- FM 通道（B4）系数 -1/2（V < 0，**直接吸引**，但只对 spin-triplet 成立）

[来源] Scalapino 1995 Phys. Rep. 250, 329

### 3.3 spin-triplet 配对函数

[定义] spin-triplet 配对需要 odd-parity 轨道函数 + S=1 自旋：
$$\hat{\Delta}_{\alpha\beta}(\mathbf{k}) = i (\mathbf{d}(\mathbf{k}) \cdot \boldsymbol{\sigma})_{\alpha\beta} \sigma_y$$

其中 **d(k)** 是三维 d 矢量（"d-vector"），描述配对自旋方向。

[关键性质]
- d(-k) = -d(k)（odd parity）
- |d(k)| 是能隙幅度
- d̂ 方向决定自旋极化方向

### 3.4 三种典型配对

| 配对 | d(k) | 备注 |
|------|------|------|
| ESP（Equal-Spin Pairing）| d × 自旋平面外 | A 相 in ³He |
| Polar | d ∥ 单一方向 | B 相 in ³He |
| chiral p+ip | d_x ± i d_y | TRSB |
| Helical p | d_x sin k_x + d_y sin k_y | 拓扑 |

---

## 4. spin-triplet 的判据（实验难点）

[反幻觉警告] **spin-triplet 实验证认极其困难**，许多"候选"被否决。需要**多重独立证据**。

### 4.1 Pauli limit 违反（A6）

[定义] 标准 Pauli limit：μ_BHp = Δ₀/√2 → Hp[T] ≈ 1.84·Tc[K]

spin-triplet SC 自动违反此极限（Zeeman 能不直接破对）。

[案例]
- UTe₂ c-axis：Hc2 > 30 T 远超 Pauli ~3 T
- URhGe re-entrant 至 12 T（Pauli ~0.5 T）
- Eu-nickelate Yang 2026：45 T 仍未压制

### 4.2 NMR Knight shift 在 SC 态保持

[关键判据] spin-triplet 配对**不**改变正常态自旋极化率（Knight shift 不随 SC 转变下降）。

[历史教训] Sr₂RuO₄ 1998-2019 年被认为是 chiral p+ip，原始 Knight shift 测量"无下降"。但 2019 年 Pustogow et al. 修正实验后**发现下降** → 推翻 spin-triplet 假说，改为 d 波。

[来源] Pustogow et al. 2019 Nature 574, 72 [DOI: 10.1038/s41586-019-1596-2]

[反谄媚警告] 这是凝聚态物理史上**经典教训**：单一 NMR 实验可能误导整个领域 20 年。spin-triplet 主张必须多重独立验证。

### 4.3 µSR 零场弛豫（TRSB 信号）

[判据] chiral p+ip 等时间反演破缺（TRSB）态在 SC 转变下出现 µSR 零场弛豫率增大。

[案例]
- Sr₂RuO₄：观察到 TRSB 信号 → 现在与 d 波解释相矛盾，争议进行中
- UTe₂：µSR 见 TRSB 信号 [Sundar 2019]

### 4.4 极化中子 vs 自旋密度

[判据] 偏振中子衍射可直接测自旋密度分布。

### 4.5 4π 周期 Josephson 效应

[判据] spin-triplet（特别 p+ip + 拓扑）会给出 4π 周期 Josephson 电流（Majorana 标志）。但实验确认困难。

### 4.6 双比热跃变 / 多重 SC 相

[案例] UPt₃ 在 0.5 K 附近有两个相变温度 → 多重 SC 相（spin-triplet 候选证据）

---

## 5. 关键体系数据

### 5.1 重费米子 FM SC（D8 — 待精读）

| 材料 | T_c (K) | T_FM (K) | 备注 | 来源 |
|------|---------|---------|------|------|
| **UGe₂** | 0.8（高压）| 53 | 压力下 FM + SC 共存 | Saxena 2000 |
| **URhGe** | 0.25 | 9.5 | 常压 FM + SC | Aoki 2001 |
| **UCoGe** | 0.6 | 2.5 | 极弱 FM + SC | Huy 2007 |
| **UTe₂** | 1.6 | — | 接近 FM QCP，无长程 FM 序 | Ran 2019 |

[来源]
- Saxena et al. 2000 Nature 406, 587 [DOI: 10.1038/35020500]
- Aoki et al. 2001 Nature 413, 613 [DOI: 10.1038/35098048]
- Huy et al. 2007 PRL 99, 067006
- Ran et al. 2019 Science 365, 684 [DOI: 10.1126/science.aav8645]

[观察] 重费米子 FM SC 共有特征：
- T_FM > T_c（FM 在更高温度建立）
- SC 出现在 FM 区或 FM QCP 附近
- Hc2 严重违反 Pauli limit
- 多重 SC 相（field-induced 或压力-induced）

### 5.2 URhGe Field-induced Re-entrant SC（A6 关联）

[来源] Lévy et al. 2005 Science 309, 1343 [DOI: 10.1126/science.1115498]

URhGe 在低场（< 2 T）有 SC，2-12 T 间 SC 消失，**12 T 重新出现** SC。

[物理] 高场使 FM 量子临界点位置变化 → 涨落增强 → 配对增强。

### 5.3 ³He（教科书 spin-triplet 超流）

[历史] ³He 是第一个被严格证实的 spin-triplet 超流体（Osheroff, Lee, Richardson 1972 → 1996 Nobel）。

| 相 | 温度 | 配对 |
|----|------|------|
| ³He A | 2.5 mK | ESP, A 相 |
| ³He B | 1.0 mK | BW 状态（可旋）|
| ³He A1 | < B1 | 极化 A 相 |

[来源] Anderson-Brinkman-Morel 1972; Vollhardt-Wölfle 1990 教科书

### 5.4 Sr₂RuO₄ 历史争议

[历史] 1998-2019 年被广泛认为是 chiral p+ip。2019 年 Pustogow Knight shift 修正 → **撤销** chiral p+ip 解释。

[现状] 多数共识转向 d_xy 或 s±d 等单态配对。但 µSR TRSB 信号仍在 → 部分 chiral 元素可能保留。

[来源] Mackenzie-Maeno 2003 RMP（早期综述）+ Pustogow 2019 + 多篇后续

[反谄媚警告] **这是 21 世纪凝聚态物理最大错误案例**。任何 spin-triplet 主张必须谨慎。

### 5.5 UTe₂（最新候选，仍存争议）

| 量 | 值 | 来源 |
|----|----|------|
| T_c | 1.6 K | Ran 2019 |
| Hc2 c-axis | > 30 T | Aoki 2019 |
| Hc2 / Pauli limit | > 10× | 同上 |
| Knight shift | 部分下降（争议）| 多篇 |
| µSR TRSB | 有信号 | Sundar 2019 |
| 节点结构 | 待定 | 多篇 |

[反幻觉] UTe₂ 是当前 spin-triplet 最强候选，但**不能宣称已确认**。Knight shift 数据仍存争议（与 Sr₂RuO₄ 历史教训相似）。

### 5.6 Eu-doped Nickelate（Yang 2026 — 已精读）

[来源] Yang et al. 2026 Nature [arXiv:2508.14666]

**Sm₀.₉₅₋ₓCa₀.₀₅EuₓNiO₂** 在 x = 0.30-0.55 区域：
- **铁磁有序 + SC 共存**（首次在镍酸盐中观察）
- Field re-entrant SC 至 45 T
- 暗示 spin-triplet 候选

[观察] 这是 Tc ~10 K 体系首次明确的 FM + SC 共存案例。比传统重费米子（Tc < 1 K）高 10×。

[反幻觉] 论文**没有直接证明** spin-triplet（论文标题为 "Field re-entrant superconductivity"，机制留作开放问题）。spin-triplet 是**可能解释之一**。

---

## 6. FM 涨落的限制

[反谄媚] 必须明确：

### 6.1 强 FM 抑制 SC

实际上**强 FM 序破坏 SC**（即使是 triplet）：
- 大磁场（内场）→ 轨道效应破对
- 自旋极化破坏 ESP

→ FM SC 通常出现在 **FM QCP 附近**或**弱 FM** 区，不在强 FM 内部。

### 6.2 实验证认极困难

| 判据 | 局限 |
|------|------|
| Knight shift | 反例多（Sr₂RuO₄ 教训）|
| µSR TRSB | 必要但不充分 |
| Pauli violation | 可能源于 FFLO 等其他机制 |
| 4π Josephson | 实验难，争议多 |

### 6.3 缺乏 ab initio 框架

类比 B3：FM χ_s(0, 0) 难第一性原理计算，多用唯象/RPA。

### 6.4 拓扑 SC + spin-triplet 重叠

p+ip 的 spin-triplet 与拓扑 SC 重叠 → Majorana 候选。但实验区分 trivial 与 topological 困难（A9 Andreev ZBCP 案例）。

### 6.5 与 AFM 涨落区分

实际体系往往**多机制并存**：
- UTe₂：接近 FM QCP，但有 AFM 涨落贡献
- 镍酸盐：双层 J_⊥（AFM）+ Eu 引入 FM
- 不能简单归类

---

## 7. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B3 AFM 涨落** | **镜像对比** | 反号 vs 同号配对 |
| **C5 p 波** | **核心结果** | spin-triplet 自然给 p 波 |
| **C6 f 波** | 高阶 | 重费米子可能 |
| **C7 chiral d±id, p±ip** | 时间反演破缺 | µSR 信号 |
| **C9 singlet vs triplet** | **核心判据** | Knight shift 等 |
| **A6 临界场** | **Pauli limit 违反** | spin-triplet 自然规避 |
| **G2 SC + FM 共存** | **核心** | UGe₂, URhGe, Eu-nickelate |
| **G3 Field-induced** | **强关联** | URhGe re-entrant |
| **G4 Re-entrant** | **核心** | URhGe 12T, Yang 2026 45T |
| **G7 spin-triplet** | **同义** | spin-triplet SC 即 G7 |
| **F4-F5 拓扑 SC** | 重叠 | p+ip 候选 Majorana |
| **D5 镍酸盐** | **新方向** | Yang 2026 Eu-nickelate |
| **D8 重费米子** | **核心应用** | UGe₂/URhGe/UCoGe/UTe₂ |
| I4 NMR | 关键工具 | Knight shift |
| I6 µSR | 关键工具 | TRSB 探测 |

---

## 8. 推荐精读论文

### 必读（理论基础）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Berk-Schrieffer 1966** | DOI: 10.1103/PhysRevLett.17.433 | 含 FM 通道首发 |
| Fay-Appel 1980 | DOI: 10.1103/PhysRevB.22.3173 | FM SC 理论 |
| Anderson-Brinkman-Morel 1972 | DOI: 10.1103/RevModPhys.47.415 | ³He 配对理论 |

### 关键实验
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Saxena et al. 2000** | DOI: 10.1038/35020500 | UGe₂ 发现 |
| **Aoki et al. 2001** | DOI: 10.1038/35098048 | URhGe 发现 |
| **Lévy et al. 2005** | DOI: 10.1126/science.1115498 | URhGe re-entrant SC |
| Huy et al. 2007 PRL 99, 067006 | DOI: 10.1103/PhysRevLett.99.067006 | UCoGe |
| **Ran et al. 2019 Science 365, 684** | DOI: 10.1126/science.aav8645 | UTe₂ |

### 关键综述
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Aoki-Knebel-Flouquet 2019** | DOI: 10.7566/JPSJ.88.022001 | **必读综述** |
| Mackenzie-Maeno 2003 RMP 75, 657 | DOI: 10.1103/RevModPhys.75.657 | Sr₂RuO₄（已部分过时）|
| Vollhardt-Wölfle 1990 | "Superfluid Phases of ³He" | ³He 教科书 |

### 重要修正案例
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Pustogow et al. 2019** | DOI: 10.1038/s41586-019-1596-2 | Sr₂RuO₄ 修正经典案例 |

### 现代镍酸盐（已精读）
| 论文 | 来源 | 状态 |
|------|------|------|
| Yang et al. 2026 arXiv:2508.14666 | Eu-nickelate 45T re-entrant | 已精读 |

---

## 9. 数据汇总（反幻觉确认）

[定理 - Berk-Schrieffer 1966] V_pair^(t) = -(1/2) U² χ_s(q≈0, 0) 在 spin-triplet 通道吸引

[定理 - Stoner] 1 - U χ₀(0) → 0 时 FM 不稳定

[定理] spin-triplet 配对：Δ̂(k) = i (d(k)·σ) σ_y，d(-k) = -d(k)

[观察 - UTe₂] Tc=1.6K, Hc2 c-axis > 30T（Pauli limit ~3T 违反 10×）[Aoki 2019]

[观察 - URhGe] T_FM = 9.5K, T_c = 0.25K, 12T re-entrant SC [Lévy 2005]

[观察 - UGe₂] T_FM = 53K（常压）, T_c = 0.8K（高压）[Saxena 2000]

[观察 - Eu-nickelate Yang 2026] T_c ~10K, FM + SC 共存 x = 0.30-0.55 区, 45T re-entrant

[历史教训 - Sr₂RuO₄] 1998-2019 chiral p+ip 假说被 Pustogow 2019 Knight shift 实验推翻

---

## 10. 反幻觉自检

- [x] Berk-Schrieffer 1966 / Fay-Appel 1980 / Aoki-Flouquet 2019 经典 DOI 标注
- [x] UGe₂/URhGe/UCoGe/UTe₂ 各自数据来源（Saxena/Aoki/Huy/Ran）
- [x] Eu-nickelate 数据 Yang 2026 (arXiv:2508.14666)
- [x] **Pustogow 2019 Sr₂RuO₄ 修正案例明确说明**（凝聚态最大错误案例）
- [x] V_pair^(t) = -(1/2) U² χ_s 系数与 B3 (3/2) 系数对比清晰
- [x] **不假装 UTe₂ 已确认 spin-triplet**（仍存争议）
- [x] **不假装 Yang 2026 已证明 spin-triplet**（论文留作开放问题）

---

## 11. 反谄媚自检

- [x] **Sr₂RuO₄ 历史教训明确说明**（凝聚态物理 21 世纪最大错误案例）
- [x] spin-triplet 实验证认困难明确（多重判据必需）
- [x] 强 FM 抑制 SC 的事实坦诚（FM SC 在 QCP 附近）
- [x] UTe₂ 未确认 spin-triplet 明确
- [x] Yang 2026 暗示 spin-triplet 但论文未声明
- [x] 多机制并存（FM + AFM + 轨道）现实说明
- [x] 不夸大重费米子 FM SC 综述完备性（Aoki 2019 仅基础综述）

---

## 12. 当前状态与后续行动

**状态：** [已综述]

**关键洞察总结：**

1. **B4 与 B3 数学上互补**：AFM 给 singlet d 波，FM 给 triplet p/f 波
2. **spin-triplet 实验证认极困难**（Sr₂RuO₄ 教训）
3. **重费米子是 FM SC 标准应用**（UGe₂/URhGe/UCoGe/UTe₂）
4. **Eu-nickelate Yang 2026 是 Tc ~10K 体系新候选**（10× 高于重费米子典型 Tc）
5. **Pauli limit 违反是 spin-triplet 必要不充分条件**

**遗留问题：**
1. UTe₂ Knight shift 数据修正可能性（Sr₂RuO₄ 教训）
2. Eu-nickelate 是否真为 spin-triplet（→ Yang 2026 后续 + Knight shift 实验）
3. 4π Josephson 效应在 UTe₂ 的实验确认
4. 重费米子 FM SC 的 ab initio 理论（强关联 + Kondo + 配对）
5. 镍酸盐配对机制争议（s± vs spin-triplet 候选）

**对 Paper E 的关联：**
[反谄媚] Paper E 默认 spin-singlet 框架，**不适用 spin-triplet 体系**。Yang 2026 的 spin-triplet 暗示是 Paper E 的明确边界 — 膜框架需扩展到 triplet 才能涵盖。

**对 Paper A 的关联：**
- Paper A 的 λ_sf 默认 AFM 通道（B3）
- FM 通道（B4）λ_FM 在 Paper A 中**未明确**
- 这是 Paper A 的潜在扩展方向

**后续：** B5（向列涨落 NFMS）— 与 AFM/FM 完全不同的"序参量涨落"通道（Romero 2026 FTS 关键解释）

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。AFM vs FM 镜像对比 + 重费米子 FM SC + Sr₂RuO₄ 教训 + Yang 2026 Eu-nickelate 现代候选
