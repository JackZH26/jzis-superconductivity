# A. 现象学（Phenomenology）— 详细研究清单

**MECE 编号：** A
**问的维度：** "看到了什么？"（实验观测层面）
**子课题数：** 10
**版本：** v1.0 (2026-04-27)
**遵循规则：** `../00_RULES.md`

---

## 维度定义

A 部分关注**实验观测的现象**，不关心微观机制。每个子课题对应一个标志性的实验观测。这是研究超导的"输入层"——任何理论必须解释这些现象。

---

## A1. 零电阻（Zero Resistivity）

### 物理定义
当 T < Tc 时，超导体的直流电阻率 ρ = 0（在仪器精度内）。

### 关键测量量
| 量 | 含义 | 典型数值 |
|----|------|---------|
| Tc | 临界温度（onset / midpoint / 90%-10% / zero-resistance）| 因材料而异 |
| ρ_n(Tc) | 正常态电阻率（Tc 上方）| µΩ·cm 量级 |
| 持续电流寿命 | 闭合回路电流衰减时间 | > 10⁵ 年（实验下限）|

### 历史关键节点
- **1911**：Onnes 发现水银 4.2 K 超导[H. K. Onnes, Comm. Phys. Lab. Univ. Leiden 120b]
- **1933**：完全抗磁性发现使"完美导体"和"超导体"得以区分

### 测量方法
- 四探针法（消除接触电阻）
- 持续电流衰减实验（最严格的 ρ=0 验证）

### 已知例外/复杂情形
- **超导涨落**：Tc 附近 ρ 平滑下降，不是阶跃
- **2D 体系**：BKT 转变 → 超导起来不完全
- **无序系统**：Anderson 局域化（不同于 SC 的零电阻）
- **非平衡态**：光致超导是瞬态

### 与其他 MECE 关联
- A2（Meissner）— 配对的两个独立实验证据
- A6（临界场）— H>Hc 时 ρ 重现
- E7（无序）— Anderson 定理边界
- H1（strange metal）— 正常态 ρ 异常

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Onnes 1911 | 必读经典 |
| 综述 | Tinkham《Introduction to Superconductivity》Ch.1 | 教科书 |

### 当前状态
**[已掌握]** — 不需要精读，写一篇 A1 综述说明即可。

---

## A2. Meissner 效应（完全抗磁性）

### 物理定义
T < Tc 时，超导体内部磁场 B = 0（除表面 λ_L 厚度外）。这是与"完美导体"的本质区别。

### 关键测量量
| 量 | 含义 | 典型数值 |
|----|------|---------|
| χ | 磁化率 | -1（SI 单位）|
| λ_L | London 穿透深度 | 100–10000 Å |
| Hc1 | 类型 II 下临界场 | mT–T 量级 |
| Hc2 | 上临界场 | T–10T+ 量级 |

### 历史关键节点
- **1933**：Meissner & Ochsenfeld 在锡和铅中发现 [Naturwissenschaften 21, 787 (1933)]
- **1935**：F. & H. London 给出唯象方程

### 测量方法
- DC 磁化率（SQUID 磁强计）
- AC 磁化率（互感测量）
- µSR（局部磁场分布）
- 极化中子（穿透深度）

### Type I vs Type II
| 类型 | κ = λ_L/ξ | 行为 |
|------|---------|------|
| Type I | κ < 1/√2 | 单一 Hc，全完全抗磁 |
| Type II | κ > 1/√2 | Hc1 < H < Hc2 涡旋态 |

### 已知例外/复杂情形
- **拓扑磁通**：FFLO 态 + 涡旋核内电子结构
- **强 SC 涨落体系**：µSR 看到的"超导体积分数"<100%（如 Bozovic 2016 LSCO）
- **"Reentrant" 表观 Meissner**：Eu-nickelate 高场重新出现 Meissner（Yang 2026）

### 与其他 MECE 关联
- A1（零电阻）— 配对的两个独立证据
- A6（临界场）
- F（量子几何）— 几何超流权重
- E5（磁场）

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Meissner-Ochsenfeld 1933 | 必读经典 |
| 关键 | Bozovic et al. 2016 Nature 536, 309 | 已有精读笔记 |
| 综述 | Tinkham Ch.1-2 | 教科书 |

### 当前状态
**[已掌握]** — 写综述即可，含 Bozovic 2016 关键数据。

---

## A3. 比热跃变（Specific Heat Jump）

### 物理定义
Tc 处比热 C(T) 出现阶跃 ΔC：
```
ΔC/γTc = 1.43（弱耦合 BCS 普适值）
```
其中 γ 是正常态 Sommerfeld 系数（C_n = γT）。

### 关键测量量
| 量 | 含义 | BCS 值 |
|----|------|--------|
| ΔC/γTc | 跃变标度 | 1.43 |
| γ | 正常态 Sommerfeld 系数 | mJ/(mol·K²) 量级 |
| α = ΔC/(γTc) | 跃变比 | 强耦合可达 2-3 |

### 强耦合修正
| 材料 | ΔC/γTc | 备注 |
|------|--------|------|
| Al | ~1.45 | 弱耦合 |
| Pb（α-Pb）| ~2.7 | 强耦合 |
| MgB₂ | ~0.8（σ 带）+ ~0.2（π 带）| 双能隙 |
| 铜氧化物 | ~3-5 | 非常规 |

### 测量方法
- AC 比热（高灵敏度）
- DC 比热（绝热）
- 弛豫法

### 已知例外/复杂情形
- 多能隙体系：多个跃变（MgB₂, FeSe）
- 节点 SC（d-wave）：T³ 项+残余线性 T 项

### 与其他 MECE 关联
- A5（能隙）— ΔC ∝ Δ²
- B1（BCS）— 1.43 是 BCS 预测
- B2（Eliashberg）— 强耦合修正

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Carbotte 1990 RMP | 强耦合数据集 |

### 当前状态
**[已掌握]** — 写综述即可。

---

## A4. 同位素效应（Isotope Effect）

### 物理定义
临界温度对原子质量的依赖：
```
Tc ∝ M^(-α)
```
其中 α 是同位素效应指数。

### 历史里程碑
- **1950**：Maxwell（Phys. Rev. 78, 477）和 Reynolds 等独立实验
- 在 Hg 中：α ≈ 0.5（与 BCS 1957 预测一致）
- 这是 BCS 声子机制的关键证据之一

### 关键数值
| 材料 | α | 含义 |
|------|---|------|
| Hg | 0.50 | 标准 BCS |
| Pb | 0.45 | 强耦合修正 |
| Ru | 0.00 | 非声子机制 |
| ZrAl₃ | -0.7 | 反常 |
| 铜氧化物 | 0.05–0.5 | 复杂，掺杂依赖 |
| MgB₂ | 0.30（B 同位素）| 部分声子 |
| MATBG | 待测 | 平坦带情形未明 |

### 例外的物理含义
- α=0：声子不参与
- α<0：晶格软化
- α 异常大：强耦合 + 各向异性声子

### 与其他 MECE 关联
- B1-B2（声子机制）— α 是判据
- B3-B5（非声子）— α=0 是判据
- D1-D7（家族）— 各家族 α 分布

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Maxwell 1950 | 必读 |
| 综述 | Carbotte 1990 | 数据汇总 |

### 当前状态
**[已掌握 - 基础 BCS]，[待补 - 非常规家族同位素效应数据系统化]**

---

## A5. 能隙特征（Gap Features）

### 物理定义
能隙 Δ = 准粒子激发的最小能量。BCS 弱耦合：
```
2Δ/kBTc = 2π·exp(-γ_E) ≈ 3.528
```
其中 γ_E 是 Euler-Mascheroni 常数。

### 关键测量量
| 量 | BCS 值 | 测量方法 |
|----|--------|---------|
| 2Δ/kBTc | 3.528 | 隧穿/IR/STM |
| 节点角分布 | 各向同性 / 4 节点 / 6 节点 | ARPES + STM |
| 多能隙 | 单值 / 多值 | µSR + 隧穿 |

### 强耦合修正
| 材料 | 2Δ/kBTc | 类型 |
|------|---------|------|
| Al | 3.5 | 弱耦合 |
| Pb | 4.3 | 强耦合 |
| Hg-1223 | 8 (Li 2026 ARPES) | 非常规强 |
| YBCO | ~5-6 | d 波 |
| MgB₂ | 4.0 (σ) + 1.0 (π) | 双能隙 |
| H₃S | ~5-6 | 强耦合声子 |

### 节点结构
| 配对 | 节点数 | 标识 |
|------|-------|------|
| s | 0 | C(T) ∝ exp(-Δ/T) |
| d_x²-y² | 4 | C(T) ∝ T² 至低 T |
| d_xy | 4 (旋转) | 同上 |
| p | 2 | T 反常 |
| f | 6 | 复杂 |

### 与其他 MECE 关联
- A3（比热）— Δ²/T² 关系
- A6（临界场）— Pauli limit ∝ Δ
- C1-C10（配对对称性）— 节点结构判据
- I1-I9（实验技术）— 各种探测能隙手段

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Carbotte 1990 RMP | 强耦合数据 |
| 关键 | Li 2026 ARPES (La₃Ni₂O₇) | 已有精读 |
| 综述 | Hardy 1993（YBCO 节点）| 待精读 |

### 当前状态
**[已部分掌握]** — Paper E 已涉及；需要写 A5 综述涵盖各家族 2Δ/kBTc 分布。

---

## A6. 临界场（Critical Fields）

### 物理定义
- **Hc1**（下临界场）：磁通线开始进入（仅 Type II）
- **Hc2**（上临界场）：超导完全消失
- **Hc3**（表面超导）：Hc2 < H < Hc3，仅薄层超导
- **Pauli paramagnetic limit**：μBHp = Δ/√2

### 关键标度律
| 公式 | 含义 |
|------|------|
| Hc2(0) = -0.69·Tc·(dHc2/dT)|_Tc | WHH 公式 |
| ξ_GL² = Φ₀/(2π·Hc2) | GL 关联长度 |
| λ_L² = m*c²/(4πne²) | London 穿透深度 |
| κ = λ_L/ξ | GL 参数 |

### 例外
- **UTe₂**：Hc2 远超 Pauli limit（spin-triplet）
- **Eu-nickelate**：Re-entrant SC 至 45T（Yang 2026）
- **拓扑超导**：Majorana 出现可能改 Hc2 标度

### 与其他 MECE 关联
- A2（Meissner）— Hc1, Hc2 是 Meissner 边界
- A5（能隙）— Pauli limit ∝ Δ
- E5（磁场）— 调控参数
- G5-G7（磁性互动）— Pauli violation, triplet

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Werthamer-Helfand-Hohenberg 1966 | WHH 公式 |
| 关键 | UTe₂ Hc2 异常综述 | 待精读 |
| 关键 | Yang 2026 Eu-nickelate 45T | 已有精读 |

### 当前状态
**[已部分掌握]** — 写综述涵盖 Pauli limit 违反案例。

---

## A7. 临界电流（Critical Current）

### 物理定义
超导体能承载的最大电流密度 Jc，超过则 SC 破坏。

### 三个层级
| 层级 | 含义 | 决定因素 |
|------|------|---------|
| Jc_dep | 拆对临界 | Δ/(eλv_F) |
| Jc_gl | GL 临界 | Hc/(λ_L) |
| Jc_obs | 实测 | 涡旋钉扎主导 |

### 工程意义
- 应用直接相关（K1-K10 在 Plan_BATCH_2 中）
- REBCO 商业化关键：高 Jc + 长线一致性
- 涡旋钉扎工程：缺陷工程提高 Jc

### 关键数据
| 材料 | Jc(T=4.2K, B=0) | 备注 |
|------|----------------|------|
| Nb-Ti | ~3000 A/mm² (5T) | MRI 标准 |
| Nb₃Sn | ~3000 A/mm² (12T) | ITER 用 |
| YBCO 带材 | ~10⁵ A/mm² (1T, 77K) | 高 |

### 与其他 MECE 关联
- A2（Meissner / 涡旋）
- A6（临界场）
- E7（无序）— 钉扎中心工程
- K1-K10（应用）

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 综述 | Ruiz et al. 2024 综述（高 Jc 物理）| 待精读 |

### 当前状态
**[已部分掌握]** — 工程视角，与基础物理研究不直接相关，可低优先。

---

## A8. 输运反常（Linear-T 电阻率 / Strange Metal）

### 物理定义
正常态电阻率随温度线性变化：
```
ρ(T) = ρ₀ + AT
```
直至高温（远超 Debye 温度，T_D），违反 BCS 期望的 T² 行为。

### 关键判据
| 行为 | T 依赖 | 物理 |
|------|--------|------|
| ρ ∝ T | 线性 | Strange metal / Planckian |
| ρ ∝ T² | 二次 | Fermi liquid |
| ρ → 0 | 零 | 超导 |

### Planckian 极限
散射率达到量子极限：
```
ℏ/τ = α·k_BT, α ~ 1-3
```

### 关键数据（Romero 2026 FTS, 已精读）
| 样品 | α (Planckian 乘数) |
|------|------------------|
| FeTe₀.₅₅Se₀.₄₅ | 3.02 |
| FeTe₀.₆₅Se₀.₃₅ | 2.42 |

铜氧化物（Legros et al. 2019）：
- LSCO α ~ 1
- Bi-2212 α ~ 1.2

### 测量方法
- DC 电阻率（标准 4 端）
- TDTS（直接测 σ(ω,T)，分通道）
- 高温红外光谱

### 与其他 MECE 关联
- B3-B5（非声子机制）— 线性 T 暗示量子临界
- D3, D4, D5（铜氧、铁基、镍酸盐）— 都呈现 strange metal
- H1, H2（strange metal, Planckian）— 正常态特征
- H8（双通道输运）— Romero 2026 双 Drude 解析

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Bruin et al. 2013 Science 339, 804 | Planckian 普遍性 |
| 关键 | Legros et al. 2019 Nat Phys | 铜氧 Planckian |
| 关键 | Romero 2026 Nat Phys | 已有精读 |
| 综述 | Hartnoll & Mackenzie 2022 RMP | strange metal 综述 |

### 当前状态
**[正在研究]** — Romero 2026 已精读，应做 A8 综述。

---

## A9. Andreev 反射（Andreev Reflection）

### 物理定义
当电子能量 E < Δ 时，从正常金属（N）入射 N/S 界面，反射回 hole（不是电子）+ 在 SC 中形成 Cooper 对。

### 关键观察量
- 零偏压电导峰（Zero-Bias Conductance Peak, ZBCP）
- BTK 模型拟合 Z 参数
- ZBCP 在拓扑 SC 中可能由 Majorana 末态导致

### 历史
- **1964**：Andreev 提出 [Sov. Phys. JETP 19, 1228]
- **1982**：Blonder-Tinkham-Klapwijk (BTK) 模型 [PRB 25, 4515]

### 测量方法
- 点接触（Point-Contact Andreev Reflection, PCAR）
- 平面 N/S 隧穿结
- 扫描隧道显微镜 + Andreev 模式

### 在拓扑 SC 中的角色
- **Majorana ZBCP**：无 disorder 时 ZBCP 高度 = 2e²/h（量子化）
- 但区分 Majorana vs trivial Andreev 状态是开放问题
- 大量声称 Majorana 的论文用 ZBCP 但争议大

### 与其他 MECE 关联
- A5（能隙）— 探测 Δ
- C5, C7（p-wave, chiral）
- F4-F5（拓扑超导, Majorana）
- D12（拓扑 SC 候选）

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Andreev 1964 | 经典 |
| 模型 | BTK 1982 PRB 25, 4515 | 必读 |
| 拓扑 | Wiesendanger group Majorana 综述 | 待精读 |

### 当前状态
**[空白]** — 需要单独研究，特别在拓扑 SC 背景下。

---

## A10. 准粒子干涉（QPI - Quasi-Particle Interference）

### 物理定义
STM 测量电子驻波模式（杂质散射产生的实空间干涉条纹），通过 FFT 反推 k 空间散射矢量 q。

### 数学
```
ρ(r,E) = Σ |ψ_k|² 在 r 处密度
散射 k → k' 产生 q = k' - k 的条纹
FFT[ρ(r,E)] → ρ(q,E) → 重建能带和能隙
```

### 测量方法
- STM（DC 模式 + 微分电导谱）
- 在低温（mK 级）下完成

### 关键应用
- **铜氧化物**：探测 d 波节点
- **铁基**：测 s± 配对（带间散射符号）
- **镍酸盐**：尚未有高质量 QPI 数据
- **拓扑 SC**：探测 Majorana 边态

### 历史里程碑
- **2002**：Hoffman-Kapitulnik 在 Bi-2212 看到 QPI（Science）
- **2006**：Hanaguri 在 Ca-122 看到铁基 QPI
- **2010+**：QPI 成为标准技术

### 与其他 MECE 关联
- A5（能隙各向异性）
- A9（Andreev — 都是 STM 谱）
- C1-C10（对称性诊断）
- D3, D4, D5（高质量 QPI 集中在这些家族）

### 推荐精读
| 优先 | 论文 | 备注 |
|------|------|------|
| 历史 | Hoffman et al. 2002 Science | Bi-2212 |
| 关键 | Hanaguri 2006/2009 | 铁基 QPI |
| 综述 | Fischer et al. 2007 RMP | STM in SC |

### 当前状态
**[空白]** — 需要补完，特别是 QPI 用于配对对称性诊断。

---

## 整体执行优先级（A 部分）

### 🥇 优先（已有数据 + 理论核心）
- **A8 综述** — Romero 2026 已精读，材料齐全，1 周可完成
- **A5 综述** — Paper E 已研究，补强各家族 2Δ/kBTc 分布

### 🥈 次优先（教科书内容 + 关键论文）
- A1, A2, A3, A4, A6 综述 — 大部分已掌握，写综述化操作
- A7 综述 — 工程导向，可简化

### 🥉 第三优先（空白补全）
- A9 Andreev — 在拓扑 SC 背景下深入（与 D12 关联）
- A10 QPI — 与 A5 联动（节点诊断）

---

## 存档计划

| 文件名 | 内容 | 状态 |
|--------|------|------|
| `A_overview.md` | 本文档 | ✅ 已建立 |
| `A1_zero_resistivity_overview.md` | A1 综述 | ⏸️ 待写 |
| `A2_meissner_effect_overview.md` | A2 综述 | ⏸️ 待写 |
| `A3_specific_heat_jump_overview.md` | A3 综述 | ⏸️ 待写 |
| `A4_isotope_effect_overview.md` | A4 综述 | ⏸️ 待写 |
| `A5_gap_features_overview.md` | A5 综述 | ⏸️ 待写 |
| `A6_critical_fields_overview.md` | A6 综述 | ⏸️ 待写 |
| `A7_critical_current_overview.md` | A7 综述 | ⏸️ 待写（低优先）|
| `A8_linear_T_strange_metal_overview.md` | A8 综述 | ⏸️ 待写（高优先）|
| `A9_andreev_reflection_overview.md` | A9 综述 | ⏸️ 待写 |
| `A10_QPI_overview.md` | A10 综述 | ⏸️ 待写 |

每个 overview 完成后，按论文需要做单篇精读笔记：
```
A8_LinearT_Romero2026NatPhys_精读_2026-04-25.md
A8_LinearT_Legros2019NatPhys_精读_YYYY-MM-DD.md
A8_LinearT_Bruin2013Science_精读_YYYY-MM-DD.md
A8_LinearT_HartnollMackenzie2022RMP_精读_YYYY-MM-DD.md
```

---

## 与其他 MECE 编号的依赖图

```
A1 ──┬── A2 (配对的两个证据)
     ├── A6 (Hc 处零电阻恢复)
     └── E7 (无序破坏)

A2 ──┬── A6 (Meissner-临界场)
     ├── F1 (London-Quantum geometry)
     └── E5 (磁场调控)

A3 ── A5 (ΔC ∝ Δ²)
     └── B1, B2 (BCS, Eliashberg)

A4 ── B1-B14 (机制判据)
     └── D1-D15 (各家族数据分布)

A5 ── C1-C10 (节点 → 对称性)
     ├── A3 (比热)
     ├── A6 (Pauli limit)
     ├── A9 (Andreev)
     └── A10 (QPI)

A8 ── H1, H2, H8 (Strange metal 是核心)
     ├── B3-B5 (机制起源)
     └── D3, D4, D5 (主要家族)

A9 ── F4-F5 (拓扑超导, Majorana)
     └── D12 (拓扑超导候选)

A10 ── A5, A9 (节点诊断)
      └── D3, D4, D5 (主要应用家族)
```

---

## 期望产出

完成 A 部分（10 个综述）后：
- 每个子课题有清晰的物理图像
- 各家族在每个现象上的位置已标注
- 与其他 MECE 编号的依赖关系清晰
- 为后续 B-H 部分研究提供"现象学坐标系"

**预期总投入：** 4-8 周（全部 10 个综述）

**最优先：** A8 + A5（与 Paper A、Paper E 直接相关，且已有大量精读笔记基础）。
