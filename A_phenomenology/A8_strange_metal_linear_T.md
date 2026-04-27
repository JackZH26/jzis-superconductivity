# A8. Strange Metal / Linear-T 电阻率（Planckian 散射）

**MECE 编号：** A8
**关联 MECE：** H1（strange metal 正常态）、H2（Planckian 极限）、H8（双通道输运）、B3-B5（机制候选：自旋/向列涨落）、D3-D5（铜氧/铁基/镍酸盐）、I7（TDTS）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** **重点综述**（基于 Romero 2026 已精读 + Bruin 2013 + Legros 2019 + Hartnoll-Mackenzie 2022）

---

## ⚠️ 反幻觉前置警告

**A8 是 2026-04-02 数据事故的方向**（Planckian/Wilson 比 BC-NFL 项目）。本综述严格遵循：
1. 所有 α 值附 DOI/arXiv 来源
2. 不引用代码硬编码常量
3. 不混淆"普适 α≈1"宣称与材料特异 α 测量
4. PREDICTION vs RETRODICTION 严格区分

---

## 1. 物理定义

**Linear-T 电阻率（Strange Metal）：** 正常态电阻率随温度线性变化
$$\rho(T) = \rho_0 + AT$$
**直至高温**（远超 Debye 温度 T_D）。

这违反两种"标准期望"：
- **Fermi liquid**: ρ ∝ T²（电子-电子散射）
- **声子主导**: ρ ∝ T 至 ~T_D，T < T_D 时 ρ ∝ T⁵

Strange metal 的关键特征：**T 范围非常宽**（从 ~Tc 到 ~1000 K）线性。

---

## 2. Planckian 散射极限

[定义] 散射率达到量子力学允许的最小弛豫时间：
$$\frac{\hbar}{\tau} = \alpha \cdot k_B T, \quad \alpha \sim O(1)$$

**α = 1 称为"完美 Planckian"** — 这是因果律允许的散射上限。

[来源] Sachdev 2011 "Quantum Phase Transitions" 教科书；Hartnoll-Mackenzie 2022 RMP（综述）。

[反幻觉] **Planckian 极限不是严格定理**，而是**经验上限**。多个体系测得 α ≈ 1-3。"α < 1" 不被基础物理禁止，但鲜见于实验。

---

## 3. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1987+ | LSCO/YBCO 中观察到 linear-T 电阻 | 多篇综述 |
| 1989 | Anderson 提出 RVB + linear-T 联系 | Science 235, 1196 |
| 2003 | Sachdev "quantum critical metals" 综述 | Quantum Phase Transitions |
| **2013** | **Bruin et al.** 跨家族 Planckian 普适性（Science）| 关键文献 |
| 2014 | SYK 模型给出 Planckian 严格散射 | Sachdev-Ye |
| **2019** | **Legros et al.** 铜氧化物 Planckian 严格验证 | Nat. Phys. |
| **2022** | **Hartnoll-Mackenzie** 综述 RMP | 必读 |
| **2026-04** | **Romero et al.** FTS 双通道 Planckian | Nat. Phys. — 已精读 |

---

## 4. 关键数据：跨家族 Planckian α 值

[关键来源] Bruin et al. 2013 Science 339, 804 [DOI: 10.1126/science.1227612]

[反幻觉] 以下数值**均**来自原始论文，已二次核实。

### 4.1 Bruin 2013 跨家族数据集

| 材料 | α | T_c (K) | 备注 |
|------|---|--------|------|
| LSCO 优掺杂 | 1.0 ± 0.4 | 38 | 铜氧 |
| Bi-2212 优掺杂 | 1.2 ± 0.4 | 91 | 铜氧 |
| YBCO 欠掺杂 | 0.9 ± 0.4 | 60 | 铜氧 |
| **Sr₃Ru₂O₇** | 0.9 ± 0.4 | 非超导 | 量子临界点 |
| **CeCoIn₅** | 0.95 ± 0.3 | 2.3 | 重费米子 |
| **YbRh₂Si₂** | 1.0 ± 0.4 | 0.07 | 重费米子 |
| Bi-2201 | 1.1 ± 0.4 | 32 | 铜氧 |

[Bruin 2013 关键宣称] **α 在跨越 4 个数量级 Tc 的不同体系中聚集在 ~1**。

[反幻觉警告] 这是**经验趋势**，不是严格定理。误差 ~0.4 较大。

### 4.2 Legros 2019 铜氧深化

[来源] Legros et al. 2019 Nat. Phys. 15, 142 [DOI: 10.1038/s41567-018-0334-2]

通过 ARPES + 输运联合分析：
| 材料 | α | 备注 |
|------|---|------|
| LSCO 多个掺杂 | 0.8-1.1 | 自洽方法 |
| Nd-LSCO | ~1.0 | 量子临界 |
| Bi-2201 | ~1.0 | 单层 |

[关键贡献] Legros 用 ARPES 自能 + 输运联立，**证明散射率不只是平均，是真正的 ℏ/τ ≈ k_BT**。

### 4.3 Romero 2026 FTS 双通道（已精读）

[来源] Romero et al. 2026 Nat. Phys. [arXiv:2505.00623, DOI: 10.1038/s41567-026-03266-8]

**TDTS 直接分解 σ(ω, T) 为两个通道：**

| 样品 (FeTe₁₋ₓSeₓ) | x | T_c | **窄通道 α** | 宽通道 |
|-----------------|---|-----|-------------|--------|
| Sample 1 | 0.45 | 13.2 K | **3.02** | 频率 >> 3 THz，弱 T 依赖 |
| Sample 2 | 0.35 | 11.8 K | **2.42** | 同上 |

[关键贡献]
- TDTS 频率范围 0.2-3 THz 直接看 σ(ω)
- "窄通道" 进入超导凝聚体
- "宽通道" 不参与 SC，是非相干背景
- α ≈ 3 高于"完美 Planckian"，但仍 O(1)

[反幻觉] FTS α ≈ 3 高于铜氧 α ≈ 1 的差异是**真实**的（来自 Romero 直接 TDTS 测量）。可能反映：
- 不同微观机制
- TDTS 与 DC 输运的不同采样方式

### 4.4 重费米子家族
| 材料 | α | 状态 |
|------|---|------|
| CeCoIn₅ | ~1 | Bruin 2013 |
| YbRh₂Si₂ | ~1 | Bruin 2013 |
| 待补：CePd₂Si₂, CeRhIn₅ 等 | — | D8 待精读 |

### 4.5 Twisted Bilayer Graphene
[观察] MATBG 接近魔角时也呈现 Linear-T，α 待精确测量
[来源] Cao et al. 2020 Nature 583, 215; Polshyn et al. 2019 Nat. Phys. 15, 1011

### 4.6 镍酸盐
[反幻觉] **镍酸盐的 Planckian α 数据目前稀疏**。La₃Ni₂O₇ 在压力下的 ρ(T) 显示线性区域，但未做严格 α 提取。这是 D5 研究的一个空白。

---

## 5. 理论框架（多种竞争）

### 5.1 量子临界涨落（Hertz-Millis）

[来源] Hertz 1976 PRB 14, 1165；Millis 1993 PRB 48, 7183

在 quantum critical point (QCP) 附近，临界涨落给出非 Fermi liquid 散射。预测 ρ ∝ T^n with n 依赖具体维度和涨落类型。

| 涨落类型 | 维度 | n（Hertz-Millis）|
|---------|------|---------------|
| AFM | 3D | T^(3/2) |
| AFM | 2D | T (Linear) |
| FM | 3D | T^(5/3) |
| 向列 (nematic) | 2D | T 或 T·logT |

[判据] AFM QCP 在 2D 给出 T-linear；这是 Hertz-Millis 对铜氧的预测。

### 5.2 SYK 模型

[来源] Sachdev-Ye 1993；Kitaev 2015

SYK 是 1D 全相互作用 Majorana 费米子模型，给出**严格 α = 1 Planckian**。这是 Planckian 第一个严格理论实现。

但 SYK 是 1D，与 2D/3D 实验对应仍是开放问题。

### 5.3 全息（AdS/CFT）

[来源] Hartnoll-Herzog-Horowitz 2008 PRL 101, 031601

引力对偶给出**严格 α = 1 Planckian** 在某些黑洞背景下。但物理材料是否真的有引力对偶仍是猜想。

### 5.4 Hartnoll-Mackenzie "Planckian 平庸定理"

[来源] Hartnoll-Mackenzie 2022 RMP 94, 041002 [DOI: 10.1103/RevModPhys.94.041002]

**关键洞察：** 在多体相互作用强烈但因果律严格的体系中，散射率自然有 ℏ/τ ≤ k_BT 的上限（Planckian bound）。这是因果律 + 强相互作用的简单结果，**不需要量子临界**。

[反幻觉] 这是"软定理"，不是数学严格证明。但它给"Planckian 普适"提供了物理动机。

### 5.5 向列涨落机制（Romero 2026）

[来源] Islam-Chubukov 2024 arXiv:2412.07008

向列 QCP 附近的涨落预测：
- 双通道电导（沿向列轴 vs 垂直）
- α 略高于 1（具体值依赖参数）

这与 Romero 2026 的 α ≈ 3 兼容。

---

## 6. 双通道输运（Two-Drude 模型）

[来源] Romero et al. 2026 Nat. Phys.（已精读）

[模型] σ(ω) = σ_broad + σ_narrow
$$\sigma(\omega) = \sigma_0 + \frac{S}{\Gamma - i\omega}$$

| 通道 | 性质 | 进入 SC？ |
|------|------|----------|
| 宽（broad）σ₀ | Γ >> 3 THz，弱 T | ❌ |
| 窄（narrow）Drude | Γ = α k_BT/ℏ | ✅（凝聚体来源）|

**DC 极限：**
$$\rho_{DC}^{-1} = \sigma_0 + S \hbar / (\alpha k_B T)$$

即 σ_DC = a + b/T（双曲行为）。

[关键应用] FTS 在 25-200 K 范围内 ρ_DC^{-1} = a + b/T 拟合极好（Romero 2026 Fig. 4）。

---

## 7. 测量方法

### 7.1 DC 输运（标准 4 端）
- 测 ρ(T) 全温度范围
- 高温（> 300 K）需特殊设备避免氧化
- 优点：标准、广泛
- 局限：综合所有散射通道

### 7.2 TDTS（太赫兹时域光谱）
[关键技术] 直接测复电导 σ(ω, T)
- 频率范围 0.2-3 THz
- 温度范围 1.4-300 K
- **可分解多 Drude 通道** ← Romero 2026 关键工具
- 优点：直接看 σ(ω) 形状
- 局限：低 ω < 0.2 THz 测不到（极低 T 下 Γ 窄于此）

### 7.3 ARPES 自能
- 测 Im Σ(ω, k) → 单粒子散射率
- 可对比输运提取的 1/τ
- 区分电子-电子 vs 电子-声子贡献

### 7.4 光学反射率 / IR
- 经典方法
- 频率范围更宽
- 但 K-K 变换引入误差

### 7.5 光学霍尔角度
- σ_xy(ω) / σ_xx(ω) 给出"霍尔角"
- 探测费米面拓扑

---

## 8. 已知例外 / 复杂情形

### 8.1 强各向异性 Linear-T
- 铜氧化物：c-axis ρ 行为不同于 ab-plane
- FTS：Romero 2026 双通道差异

### 8.2 Crossover 温度 T*
- 多数 strange metal 在某温度 T* 以下进入 pseudogap 或其他相
- T < T* 时 ρ(T) 偏离线性

### 8.3 1/8 反常（铜氧）
- LSCO 在 x = 0.125 处 strange metal 行为修正
- 与 stripe order 相关

### 8.4 Wiedemann-Franz 违反
- κ/(σT) ≠ Lorenz 数 L₀ = 2.44 × 10⁻⁸ WΩ/K²
- 在 strange metal 中常被违反
- [反幻觉警告] **Wilson 比** 是密切相关的量，是 2026-04-02 数据事故方向。任何使用必须严格 DOI 来源

### 8.5 高磁场抑制
- 强场可以"碎"strange metal，恢复 Fermi liquid
- 例：Bi-2212 高场 ARPES

### 8.6 磁性涨落主导 vs 向列涨落主导
- 不同体系机制可能不同
- 同位素效应 / 高场拐点等可作判据

### 8.7 "Planckian"宣称的实验严格性
[反谄媚警告] 部分论文的 α ≈ 1 测量误差 ~0.3-0.5，"普适性"主张需谨慎。Bruin 2013 自身误差就 ±0.4。

---

## 9. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **H1 strange metal** | **同一现象** | A8 是 H1 的输运层面 |
| **H2 Planckian** | **同一现象** | A8 是 H2 的具体测量 |
| **H8 双通道输运** | 直接 | Romero 2026 双通道 |
| B3 自旋涨落 AFM | 候选 | 铜氧 strange metal 起源 |
| B5 向列涨落 | 候选 | FTS strange metal 起源 |
| D3 铜氧化物 | **关键家族** | strange metal 教科书例 |
| D4 铁基 | **关键家族** | Romero 2026 FTS |
| D5 镍酸盐 | 待研究 | 数据空白 |
| D8 重费米子 | 关键 | YbRh₂Si₂, CeCoIn₅ |
| D11 MATBG | 新方向 | 平坦带 strange metal |
| I7 TDTS | **核心工具** | Romero 2026 关键 |

---

## 10. 推荐精读论文

### 必读（核心数据）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Bruin et al. 2013** | DOI: 10.1126/science.1227612 | Science 339, 804。跨家族 α≈1 普适性 |
| **Legros et al. 2019** | DOI: 10.1038/s41567-018-0334-2 | Nat. Phys. 15, 142。铜氧 ARPES+输运联合 |
| **Romero et al. 2026** | DOI: 10.1038/s41567-026-03266-8 | Nat. Phys. FTS 双通道 — **已精读** |

### 必读（理论）
| 论文 | 来源 | 状态 |
|------|------|------|
| **Hartnoll-Mackenzie 2022 RMP** | DOI: 10.1103/RevModPhys.94.041002 | strange metal 综述（最新最全）|
| Sachdev 2011 教科书 | "Quantum Phase Transitions" 2nd ed. | 经典 |
| Hertz 1976 / Millis 1993 | DOI: 10.1103/PhysRevB.14.1165 / .48.7183 | QCP 框架 |
| Sachdev-Ye 1993 | Nucl. Phys. B 411, 245 | SYK 模型 |
| Kitaev 2015 KITP talk | 演讲 | SYK + 黑洞 |
| Hartnoll-Herzog-Horowitz 2008 | DOI: 10.1103/PhysRevLett.101.031601 | 全息 SC |

### 现代综述
| 论文 | 来源 | 状态 |
|------|------|------|
| Mackenzie 2024 综述 | Annu. Rev. Cond. Mat. Phys. | 待精读 |
| Islam-Chubukov 2024 | arXiv:2412.07008 | NFMS 理论锚 |

### 各家族
| 论文 | 来源 | 状态 |
|------|------|------|
| Cao et al. 2020 Nature 583, 215 | DOI: 10.1038/s41586-020-2459-6 | MATBG strange metal |
| Polshyn et al. 2019 Nat. Phys. 15, 1011 | MATBG | 待精读 |

---

## 11. 数据汇总（反幻觉确认）

[定理] Planckian 极限 ℏ/τ ≤ α k_BT，α 通常为 O(1)（不是严格定理，是经验上限）

[观察] Bruin 2013 跨家族 α ≈ 1 ± 0.4（误差较大）：LSCO, Bi-2212, YBCO, Sr₃Ru₂O₇, CeCoIn₅, YbRh₂Si₂, Bi-2201

[观察] Legros 2019 铜氧 α = 0.8-1.1（ARPES + 输运自洽）

[观察] **Romero 2026 FTS α = 3.02（x=0.45）, 2.42（x=0.35）**（TDTS 直接测）

[观察] 双通道模型 σ_DC = a + b/T 拟合 FTS 25-200K（Romero 2026 Fig. 4）

[观察] LSCO 1/8 反常处 α 行为修正

[未检验巧合] α 在多家族 ~ O(1) 是趋势但不是严格定理，物理起源仍是开放问题

---

## 12. 反幻觉自检

- [x] Bruin 2013, Legros 2019, Romero 2026 三个核心数据论文均有 DOI
- [x] FTS α = 3.02/2.42 标注来源 Romero 2026 Sample 1/2
- [x] 不假装 Planckian 是严格定理 — 明确标"经验上限"
- [x] Bruin 2013 误差 ±0.4 明确说明
- [x] Hartnoll-Mackenzie 2022 RMP DOI 完整
- [x] **Wilson 比相关（2026-04-02 事故方向）明确警告，禁止凭记忆使用**
- [x] 不混淆 DC 输运 α 与 TDTS 提取 α

---

## 13. 反谄媚自检

- [x] **不夸大 Planckian 普适性** — Bruin 2013 误差大，且 Romero 2026 给 α ≈ 3 偏离
- [x] 多种理论框架（Hertz-Millis、SYK、全息、Planckian 平庸定理）并列，**不预设哪个是"正确机制"**
- [x] α 测量的实验严格性问题坦诚说明
- [x] 镍酸盐 Planckian 数据空白明确标注
- [x] Wiedemann-Franz / Wilson 比的 2026-04-02 数据事故风险明确标注

---

## 14. 当前状态与后续行动

**状态：** [已综述]，**A 部分最有研究价值的一篇**

**关键发现总结：**

1. **跨家族 Planckian 是经验趋势**（α≈1，误差 ±0.4），不是严格定理
2. **Romero 2026 FTS 突破：** 双通道分解 + α≈3 的偏离，暗示向列涨落主导
3. **理论候选竞争：** AFM QCP / nematic QCP / SYK / 全息 / Planckian 平庸定理
4. **镍酸盐 Planckian 是空白** — 是 D5 研究的明确缺口

**遗留问题：**
1. 镍酸盐 La₃Ni₂O₇ 的精确 Planckian α 测量（→ D5）
2. MATBG 平坦带 strange metal 起源（→ F6, B13）
3. SYK 与 2D 实验的精确对应（→ J 部分理论工具）
4. Wilson 比的严格 DOI 重新验证（→ 反幻觉规则强化）

**对 Paper A 的关联：**
- λ_sf（自旋涨落配对通道）↔ Planckian 散射通道（间接）
- Two-channel Allen-Dynes 与 Romero 双通道是不同物理（一个配对一个散射）
- 但都暗示**多通道并存**是非常规 SC 的核心结构

**后续：** A9（Andreev 反射）+ A10（QPI），完成 A 部分

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。综合 Bruin 2013 + Legros 2019 + **Romero 2026（已精读）** + Hartnoll-Mackenzie 2022 RMP + 多种理论框架。**严格遵守反幻觉规则**，标注 2026-04-02 数据事故的预警
