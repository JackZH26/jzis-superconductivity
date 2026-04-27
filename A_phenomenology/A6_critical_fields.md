# A6. 临界场（Critical Fields Hc1, Hc2, Hc3）

**MECE 编号：** A6
**关联 MECE：** A2（Meissner，Hc1/Hc2 是边界）、A5（能隙，Pauli limit ∝ Δ）、C9（spin-singlet vs triplet 区分）、E5（磁场调控）、G2-G7（磁性互动核心）、F4-F5（拓扑 SC）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 GL/WHH/Maki 经典 + 现代异常案例）

---

## 1. 物理定义

### 1.1 三个临界场（Type II 超导体）

| 临界场 | 物理意义 | 边界条件 |
|--------|---------|---------|
| **H_c1** | 下临界场 | 磁通线开始进入体相（A2 Meissner 终结）|
| **H_c2** | 上临界场 | 体相超导完全消失（ρ 重现，χ → 0）|
| **H_c3** | 表面超导临界场 | Hc2 < H < Hc3 时仅 ~ξ 厚表面层超导 |

### 1.2 Type I 超导体
仅一个临界场 H_c：H < H_c 完全 Meissner，H > H_c 完全正常态。

### 1.3 GL 参数判据
$$\kappa = \frac{\lambda_L}{\xi_{GL}}$$

| κ 范围 | 类型 |
|--------|------|
| κ < 1/√2 ≈ 0.707 | Type I |
| κ > 1/√2 | Type II |

---

## 2. 磁场破坏 Cooper 对的两种机制

[关键物理] 磁场通过两个独立机制破坏 spin-singlet 配对：

### 2.1 轨道效应（Orbital Pair-Breaking）

磁场作用于电子轨道，使 Cooper 对 (k↑, -k↓) 不再是简并态。这是**Type II 上临界场的主要机制**（弱顺磁耦合时）。

[定理 - GL 1950] 在 Tc 附近，轨道临界场：
$$H_{c2}^{\text{orb}}(T) = \frac{\Phi_0}{2\pi \xi_{GL}^2(T)}$$

其中 Φ₀ = h/(2e) ≈ 2.07 × 10⁻¹⁵ Wb 是磁通量子。

[定理 - WHH 1966] 清洁极限零温外推：
$$H_{c2}^{\text{orb}}(0) \approx 0.69 \cdot T_c \cdot \left|\frac{dH_{c2}}{dT}\right|_{T_c}$$

[来源] Werthamer-Helfand-Hohenberg 1966, PRB 147, 295 [DOI: 10.1103/PhysRev.147.295]

### 2.2 顺磁效应（Pauli Paramagnetic Pair-Breaking）

磁场通过 Zeeman 能 µ_B · H 直接作用于自旋单态 Cooper 对的自旋。当 Zeeman 能超过配对能时，破对发生。

[定理 - Clogston-Chandrasekhar 1962] 顺磁极限（Pauli limit）：
$$\mu_B H_{c2}^{P} = \frac{\Delta_0}{\sqrt{2}}$$

代入 BCS Δ₀ = 1.764 k_BTc：
$$H_{c2}^{P}[T] \approx 1.84 \cdot T_c[K]$$

[来源]
- Clogston 1962, PRL 9, 266 [DOI: 10.1103/PhysRevLett.9.266]
- Chandrasekhar 1962, Appl. Phys. Lett. 1, 7 [DOI: 10.1063/1.1777362]

[关键应用] 对 Tc = 100 K 的 SC，Pauli limit ≈ 184 T（铜氧化物 H_c2 接近这个值）。

### 2.3 Maki 参数 α_M

[定义] Maki 参数衡量两种机制的相对重要性：
$$\alpha_M = \sqrt{2} \frac{H_{c2}^{\text{orb}}(0)}{H_{c2}^{P}(0)}$$

| α_M | 主导机制 |
|-----|---------|
| α_M < 1 | 轨道效应主导 |
| α_M ~ 1 | 两者同等 |
| α_M > 1 | Pauli 效应主导 |

[来源] Maki 1966, PRB 148, 362 [DOI: 10.1103/PhysRev.148.362]

---

## 3. 关键公式（速查表）

### 3.1 Hc1（Type II）
$$H_{c1} = \frac{\Phi_0}{4\pi \lambda_L^2} \ln\kappa$$

随 λ_L 增大而减小。低 Hc1 意味着易允许涡旋进入。

### 3.2 Hc2（轨道极限，清洁）
$$H_{c2}^{\text{orb}}(0) = \frac{\Phi_0}{2\pi \xi_0^2}$$

ξ₀ = ℏv_F/(πΔ₀)（清洁极限 BCS）

### 3.3 Hc3（表面超导）
[定理 - Saint-James-de Gennes 1963] 平面表面：
$$H_{c3} \approx 1.695 \cdot H_{c2}$$

[来源] Saint-James & de Gennes 1963, Phys. Lett. 7, 306 [DOI: 10.1016/0031-9163(63)90047-7]

### 3.4 Tc 附近 Hc2 斜率
$$\left|\frac{dH_{c2}}{dT}\right|_{T_c} = \frac{4\Phi_0}{\pi^2 \xi_0^2 T_c}$$

实验测量这个斜率即可外推 H_c2(0)。

---

## 4. 各家族数据

### 4.1 元素金属（Type I 多数）
| 材料 | 类型 | H_c(0) [T] | 来源 |
|------|------|----------|------|
| Al | I | 0.010 | Tinkham Ch.2 |
| Sn | I | 0.030 | Tinkham Ch.2 |
| Pb | I | 0.080 | Tinkham Ch.2 |
| Hg | I | 0.041 | Tinkham Ch.2 |
| Nb | II | H_c2 ≈ 0.4 | Tinkham Ch.4 |

[观察] 元素 Type I 的 H_c < 0.1 T，远低于 Pauli limit。

### 4.2 A15 化合物（Type II，工业用）
| 材料 | T_c | H_c2(0) [T] | 来源 |
|------|-----|----------|------|
| Nb-Ti | 9.2 K | ~14 (4.2 K) | 工业标准 |
| Nb₃Sn | 18.3 K | ~28 (4.2 K) | 工业标准 |
| Nb₃Ge | 23.2 K | ~38 (估算)| 工业 |

[应用] Nb-Ti 用于 MRI（Hc2 > 操作场 ~3T）；Nb₃Sn 用于 ITER（高场操作）。

### 4.3 高温铜氧化物（强 Type II，高 H_c2）
| 材料 | T_c | H_c2(0) [T]（c-axis）| 来源 |
|------|-----|--------------------|------|
| YBa₂Cu₃O₇ 优掺杂 | 93 K | ~120 | 多篇综述 |
| Bi-2212 | 91 K | ~150-200 | Sekitani 2003 |
| LSCO 优掺杂 | 38 K | ~65 | 多篇 |
| Hg-1223 优掺杂 | 135 K | ~190 | 估算 |

[观察] 铜氧化物的 H_c2 远超 100 T，但**接近 Pauli limit**（1.84 × 100 K ≈ 184 T）。

[来源] Sekitani et al. 2003 PRL 91, 097002（Bi-2212 高场 ARPES + Hc2）

### 4.4 铁基超导
| 材料 | T_c | H_c2(0) [T] | 各向异性 γ | 来源 |
|------|-----|----------|----------|------|
| BaFe₂(As,P)₂ | 30 K | ~50（c）| ~5 | Cho 2011 |
| FeSe | 8.5 K | ~15（c）| ~2 | Lei 2012 |
| LaFeAsO₁₋ₓFₓ | 26 K | ~70（c）| ~4 | 多篇 |

### 4.5 重费米子（Pauli limit 异常）
[关键案例] **UTe₂**：典型 spin-triplet SC 候选

| 材料 | T_c | H_c2(0) c-axis [T] | Pauli limit [T] | 比率 |
|------|-----|------------------|----------------|------|
| UTe₂ (Aoki samples) | 1.6 K | ~30+ (c) | ~3 (Pauli) | **>10×** |
| URhGe | 0.25 K | re-entrant 至 ~12 T | <0.5 | **远超** |
| UCoGe | 0.6 K | re-entrant > 20 T | ~1 | **远超** |

[来源]
- Aoki et al. 2019 Science 365, 684（UTe₂）
- Lévy et al. 2005 Science 309, 1343（URhGe re-entrant）
- 综述：Aoki, Knebel, Flouquet 2019 J. Phys. Soc. Jpn. 88, 022001

[观察] 这是 spin-triplet SC 的最强证据 — 完全规避 Pauli limit。

### 4.6 镍酸盐（Yang 2026 突破）
[关键案例] **Eu-doped infinite-layer nickelate** Sm₀.₉₅₋ₓCa₀.₀₅EuₓNiO₂：

| 样品 | T_c (零场) | Re-entrant SC 测量上限 |
|------|----------|---------------------|
| SCE0.36 | ~10 K | **45 T 仍未压制**（CHMFL Hefei）|

[来源] Yang et al. 2026 Nature [arXiv:2508.14666] — 已在 D5 精读笔记中存档

[观察] **Eu-nickelate 是首次在 ~10K 高 Tc 体系观察到 spin-triplet 候选** — 暗示镍酸盐机制可能比铜氧化物更复杂。

### 4.7 氢化物
[来源 - 待精读] H₃S, LaH₁₀ 的 Hc2 数据有限（高压实验受技术限制），但理论估算 ~ 100-200 T。

### 4.8 MgB₂
| 量 | 值 | 来源 |
|----|----|------|
| H_c2 c-axis (4.2 K) | ~3 T | 多篇 |
| H_c2 ab-plane | ~14 T | 多篇 |
| 各向异性 | ~5 | Choi 2002 Nature |

---

## 5. Maki 参数与 SC 类型分类

### 5.1 经典 Type II（轨道主导）
- α_M < 1
- 例：Nb, Nb₃Sn, MgB₂, 多数铜氧化物 in-plane

### 5.2 Pauli-limited Type II
- α_M > 1
- 例：CeCoIn₅（重费米子，FFLO 候选）
- 出现可能的 FFLO（Fulde-Ferrell-Larkin-Ovchinnikov）态

### 5.3 Pauli-violating（spin-triplet 强候选）
- 有效 α_M >> 1（H_c2 远超 Pauli limit）
- 例：UTe₂ c-axis, URhGe, UCoGe, **Eu-nickelate Yang 2026**

### 5.4 Re-entrant SC（独特相图）
- 高场重新出现 SC
- Jaccarino-Peter（G5）+ 自旋涨落增强（G4）联合机制
- 例：URhGe, UCoGe, **Eu-nickelate 45T**

---

## 6. FFLO 态（高场调制配对）

### 6.1 物理图像
[来源] Fulde-Ferrell 1964 + Larkin-Ovchinnikov 1965

当 Pauli 极限主导（α_M > 1）时，可能出现**有限动量 Cooper 对**：
$$\Psi(\mathbf{r}) \sim \cos(\mathbf{q} \cdot \mathbf{r})$$

q ≠ 0 是 FFLO 调制波矢。

### 6.2 候选材料
| 材料 | 状态 | 备注 |
|------|------|------|
| CeCoIn₅ | **强候选** | Bianchi 2003, NMR 证据 |
| 有机 SC（κ-(BEDT-TTF)₂Cu(NCS)₂）| 候选 | 各向异性 |
| 重费米子 | 部分候选 | 需更多数据 |

[来源]
- Bianchi et al. 2003 PRL 91, 187004（CeCoIn₅ FFLO）
- 综述：Matsuda-Shimahara 2007 J. Phys. Soc. Jpn. 76, 051005

### 6.3 实验签名
- Hc2 在低 T 下"凸起"（弯回）
- NMR 在高场看到自旋偶极结构
- 比热小峰

[反幻觉警告] FFLO 实验证认是争议领域，并非所有"高场异常"都是 FFLO。

---

## 7. 测量方法

### 7.1 直接磁电阻测量
- 在不同磁场下测 ρ(T)
- ρ 上升至正常值的温度为该场下 Tc(H)
- 反推 Hc2(T) → Hc2(0)

### 7.2 Tc(H) 拟合
- WHH 公式拟合 Hc2(T)
- 提取 ξ₀, λ_L, κ

### 7.3 µSR / NMR 高场
- 测 H_c1 和涡旋点阵
- 高分辨率精度

### 7.4 比热高场
- C(T,H) 拟合得 ΔC vs H
- 高场设备：CHMFL Hefei、NHMFL Tallahassee

### 7.5 高磁场设备
| 设备 | 最大场 | 类型 |
|------|--------|------|
| CHMFL Hefei | 45 T 混合 | DC + 脉冲 |
| NHMFL Tallahassee | 45 T 混合 | DC |
| LNCMI Grenoble | 36 T DC | DC |
| HZB / Dresden | ~70 T 脉冲 | 脉冲 |

[关键应用] Yang 2026 Eu-nickelate 用 CHMFL 45 T，仍未观察到 SC 消失。

---

## 8. 已知例外 / 复杂情形

### 8.1 拓扑超导
- 拓扑保护可能修改 H_c2
- Majorana 模式在高场下的稳定性

### 8.2 Bose-Einstein → BCS 过渡
- 在 BEC-BCS 跨越区，Hc2 行为不平凡
- 强关联体系

### 8.3 各向异性 SC 的 H_c2
- 各向异性比 γ = H_c2^ab / H_c2^c
- MgB₂: γ = 5
- 铜氧化物: γ = 5-100
- 各向异性 GL 公式必须使用

### 8.4 涨落区 H_c2 模糊
- 强 SC 涨落（cuprate underdoped）使 H_c2 边界不锐
- 用"onset" vs "midpoint" Tc(H) 给不同 H_c2

### 8.5 Tc 抑制 vs Hc2 增强的反相关
- 部分系统中加场使 Tc 下降但 Hc2 不严格压制
- 典型重费米子行为

### 8.6 表面 Hc3
- Hc3 通常被忽略（薄层贡献小）
- 但在薄膜样品 Hc3 可能为主导
- 需要明确区分 bulk vs surface

---

## 9. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| A2 Meissner | Hc1 边界 | Meissner 在 H < Hc1 时完全 |
| A5 能隙 | Pauli ∝ Δ | µBHp = Δ₀/√2 |
| C9 Spin singlet/triplet | **核心判据** | Pauli limit 违反是 triplet 强证据 |
| E5 磁场调控 | 直接 | 实验调控参数 |
| F1, F4-F5 量子几何/拓扑 | 修正 Hc2 | 拓扑保护修正 |
| G3-G7 磁性互动 | **核心交点** | Field-induced + Re-entrant + Jaccarino-Peter |
| I12 高场磁体 | 工具 | CHMFL, NHMFL 等 |

---

## 10. 推荐精读论文

### 必读（基础）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Werthamer-Helfand-Hohenberg 1966 | DOI: 10.1103/PhysRev.147.295 | WHH 公式 |
| Maki 1966 | DOI: 10.1103/PhysRev.148.362 | Maki 参数 |
| Clogston 1962 | DOI: 10.1103/PhysRevLett.9.266 | Pauli limit |
| Chandrasekhar 1962 | DOI: 10.1063/1.1777362 | 同期独立 |
| Saint-James-de Gennes 1963 | DOI: 10.1016/0031-9163(63)90047-7 | Hc3 |

### Spin-triplet / Re-entrant 关键
| 论文 | 来源 | 状态 |
|------|------|------|
| Lévy et al. 2005 Science 309, 1343 | URhGe re-entrant | 待精读 |
| Aoki, Knebel, Flouquet 2019 综述 | J. Phys. Soc. Jpn. 88, 022001 | 必读 |
| Ran et al. 2019 Science 365, 684 | UTe₂ | 待精读 |
| Yang et al. 2026 Nature | arXiv:2508.14666 | 已精读（D5）|

### FFLO
| 论文 | 来源 | 状态 |
|------|------|------|
| Bianchi et al. 2003 PRL 91, 187004 | CeCoIn₅ | 待精读 |
| Matsuda-Shimahara 2007 综述 | JPSJ 76, 051005 | 综述 |

### 经典综述
| 论文 | 来源 | 状态 |
|------|------|------|
| Tinkham 1996 Ch.4-5 | McGraw-Hill | 教科书 |

---

## 11. 数据汇总（反幻觉确认）

[定理] Pauli limit µ_BH_p = Δ₀/√2 = 1.247 k_BTc → H_p[T] ≈ 1.84·Tc[K]

[定理] WHH 清洁极限：H_c2^orb(0) = 0.69·Tc·|dH_c2/dT|_Tc

[定理] Hc3 ≈ 1.695·Hc2（Saint-James-de Gennes 1963）

[观察] UTe₂ c-axis Hc2 > 30 T at Tc=1.6K，是 Pauli limit 10× 以上 → spin-triplet 强证据 [Aoki 2019]

[观察] Eu-nickelate 45 T 仍未压制 [Yang 2026]

[观察] URhGe re-entrant SC 至 12 T [Lévy 2005]

[观察] Hg-1223 H_c2(c) 估算 ~190 T，接近 Pauli limit（H_p ≈ 250 T for Tc=135K）

---

## 12. 反幻觉自检

- [x] WHH/Maki/Clogston/Chandrasekhar/Saint-James 历史 DOI 标注
- [x] Pauli limit 公式 1.84·Tc[K] 来源 Clogston 1962（不混入"约 1.86" 等错误）
- [x] UTe₂ Hc2 数值标注 Aoki 2019
- [x] Eu-nickelate 45 T 标注 Yang 2026 (arXiv:2508.14666)
- [x] FFLO CeCoIn₅ 标注 Bianchi 2003
- [x] Hc3 系数 1.695 来源 Saint-James-de Gennes 1963
- [x] 不假装"所有 Pauli limit 违反 = spin-triplet" — 列出 FFLO 等替代解释

## 13. 反谄媚自检

- [x] FFLO 是争议领域，明确警告
- [x] UTe₂ spin-triplet 候选标注，不当作定论
- [x] Yang 2026 Eu-nickelate 数据列出但**不夸大**为"完全证明 spin-triplet"
- [x] WHH 公式适用条件（清洁极限弱顺磁）明确
- [x] 各向异性 H_c2 对各家族影响明确说明

---

## 14. 当前状态与后续行动

**状态：** [已综述]

**遗留问题：**
1. Eu-nickelate 45T 数据需要更长压力路径以确认 Pauli limit 突破程度（→ Yang 2026 后续 + G7）
2. UTe₂ 的精确节点结构与 H_c2 各向异性关系（→ A5, A9, C9）
3. FFLO 在镍酸盐中是否可能（开放问题）
4. 拓扑超导 Hc2 与 Majorana 稳定性（→ F4-F5）

**与 Paper E 的关联：** 如果 Yang 2026 的 spin-triplet 假说成立，Paper E 的轨道-能隙原则需要扩展到 triplet 情形。膜框架默认 singlet，是已知边界。

**后续：** A7（临界电流，工程视角）+ A8 完整综述（Linear-T 综合 Romero 2026 + 经典数据）

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。整合 Pauli limit、WHH、Maki、Saint-James 经典 + UTe₂、URhGe、Eu-nickelate、CeCoIn₅ 现代异常案例
