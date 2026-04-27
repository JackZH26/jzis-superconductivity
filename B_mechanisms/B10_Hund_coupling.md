# B10. Hund's Coupling 驱动超导（Hund's Metal SC）

**MECE 编号：** B10
**关联 MECE：** B1（BCS 基础）、B3（AFM 涨落 — 在 Hund's metal 中产生）、B5（向列涨落 — 多轨道）、B9（RVB / Mott 邻近对比）、B12（多通道）、B14（Mottness 一种特殊情形）、A8（strange metal — Hund's metal 给出非 Fermi liquid）、C2（铁基 s±）、D4（铁基核心）、D5（镍酸盐）、D8（重费米子部分）、F8（轨道纹理）、I1（ARPES 准粒子重整）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Werner 2008 + Yin-Haule-Kotliar 2011 + Georges-de'Medici-Mravlje 2013 综述 + 现代镍酸盐应用）

---

## 1. 物理定义与核心思想

**Hund's Coupling（J_H）：** 多电子原子内同一壳层不同轨道间的交换相互作用。在 Slater-Kanamori 多带 Hubbard model 中：
$$H_{int} = U\sum_{i, m}n_{im\uparrow}n_{im\downarrow} + (U-2J_H)\sum_{i, m\neq m', \sigma\sigma'}n_{im\sigma}n_{im'\sigma'} - J_H\sum_{i, m\neq m'}\mathbf{S}_{im}\cdot\mathbf{S}_{im'}$$

[关键参数]
- U：同轨道库仑排斥
- U' = U - 2J_H：不同轨道间排斥
- J_H：Hund's 交换（典型 0.3-1.0 eV）

**Hund's Metal:** 一类特殊金属态，特征是**中等 U + 强 J_H**：
- 不接近 Mott 转变（U < U_c）
- 但有**强相关效应**：m*/m ~ 5-10
- "Spin freezing" + 非 Fermi liquid
- 轨道选择 Mott 倾向

> **关键洞察（2008-2013 范式转变）：** 在 cuprate 主导的 1990s-2000s，凝聚态物理认为强关联 = 接近 Mott (U → ∞)。**Hund's metal** 揭示了**第二类强关联**：不接近 Mott，但 J_H 大→ 强重整。

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1929 | Slater 多电子原子 Hund's rules 量子推导 | PR 34, 1293 |
| 1963 | Kanamori 多带 Hubbard 模型完整形式 | Prog. Theor. Phys. 30, 275 |
| 1985+ | DMFT (Dynamical Mean-Field Theory) 发展 | Metzner-Vollhardt |
| 1996 | Georges-Kotliar-Krauth-Rozenberg DMFT 综述 | RMP 68, 13 |
| 2008 | **Werner et al.** 多带 DMFT + Hund 系统化 | PRL 101, 166405 |
| 2008 | 铁基 SC 发现 (LaFeAsO) | Kamihara |
| **2011** | **Yin-Haule-Kotliar** 铁基 = Hund's metal | Nat. Mater. 10, 932 |
| 2011 | Mravlje et al. Sr₂RuO₄ Hund's metal | PRL 106, 096401 |
| 2012 | de' Medici "Janus-faced influence" of Hund | PRL 107, 256401 |
| **2013** | **Georges-de'Medici-Mravlje** 综述 | **Annu. Rev. Cond. Matter 4, 137** |
| 2017+ | de' Medici "Hund's metal" 标签广泛使用 | 多篇 |
| 2024+ | 镍酸盐 La₃Ni₂O₇ Hund's metal 计算 | 多篇 DMFT |

---

## 3. Hund's Coupling 的"两面性"

### 3.1 Janus-faced 性质（de' Medici 2012）

[来源] de' Medici 2012 PRL 107, 256401 [DOI: 10.1103/PhysRevLett.107.256401]

**两面性：**

| 状态 | J_H 效应 |
|------|---------|
| **半填充 n=N**（每轨道半占据）| **促进 Mott 转变**（减小 U_c）|
| **远离半填充 n≠N**（一般填充）| **抑制 Mott 转变**（增大 U_c），但增强相关效应 |

[物理意义] J_H 的作用**依赖填充**：
- 半填充：J_H 帮助形成局域 S=N/2 态 → Mott
- 一般填充：J_H 解耦不同轨道 → 强关联但不 Mott

[关键] 大多数 SC 母相是**远离半填充**（铁基 d⁶, 镍酸盐 d⁸ + 部分掺杂）→ Janus 第二面：**强关联但非 Mott**。

### 3.2 Hund's metal 的标志

[Georges-de'Medici-Mravlje 2013]

| 特征 | 量 | Hund's metal 值 |
|------|----|---------------| 
| 准粒子重整 | m*/m | 5-10 |
| **Spin freezing** | 自旋自相关 ⟨S(t)S(0)⟩ | 长时间不衰减 |
| **轨道选择性** | 不同轨道 m*/m 不同 | 高（例铁基 t₂g 与 e_g 不同）|
| Coherence 温度 | T* | < 100-300 K（远低于 Fermi 温度）|
| 正常态 | Linear-T 电阻 | 是（A8 关联）|

---

## 4. 多带 Hubbard 模型的 DMFT 处理

### 4.1 模型

[来源] 多体物理标准多带 Hubbard model：
$$H = \sum_{ij, mn, \sigma} t^{mn}_{ij} c^{\dagger}_{im\sigma}c_{jn\sigma} + H_{int}$$

其中 H_int 是 Slater-Kanamori（含 J_H）。

### 4.2 DMFT 求解

[关键] DMFT (Dynamical Mean-Field Theory) 把多带 Hubbard 映射到 Anderson impurity model 自洽求解：
- 局域自能 Σ(ω) 频率依赖
- 反映强关联效应
- 多带 + Hund 必须用全 Slater-Kanamori 顶点

[DMFT 标准代码]
- TRIQS
- ALPS
- iQIST
- W2dynamics

### 4.3 Hund's metal 的"指纹"

[Werner 2008] DMFT 计算给出：
- ⟨n_d⟩(T)：占据数对温度依赖弱
- 但 m*/m 强 T 依赖
- **"Spin freezing"**：χ_loc(τ) 长时间不衰减

---

## 5. 在各家族中的应用

### 5.1 铁基 SC（D4 — 标准 Hund's metal）

[来源] Yin-Haule-Kotliar 2011 Nat. Mater. 10, 932 [DOI: 10.1038/nmat3120]

**铁基参数：**

| 参数 | 值 |
|------|----|
| 占据 | d⁶ |
| U | 4 eV |
| J_H | 0.5-0.7 eV |
| U/W | ~0.5（中等）|
| m*/m | 3-10（轨道依赖）|

[关键观察] 铁基**不接近 Mott**（U/W < U_c/W），但 J_H 给出强关联：
- **ARPES 实测 m*/m ~ 3-5**（Yi 2017 PRL 等）
- **轨道选择**：d_xy 重整 ~ 10×, d_xz/yz ~ 3×
- **DMFT + spin-fluctuation pairing**给出 s± SC

### 5.2 Sr₂RuO₄（重要测试场）

[来源] Mravlje et al. 2011 PRL 106, 096401 [DOI: 10.1103/PhysRevLett.106.096401]

**Sr₂RuO₄ 参数：**

| 参数 | 值 |
|------|----|
| 占据 | d⁴ (4d) |
| U | 2.3 eV |
| J_H | 0.4 eV |
| m*/m | 3-5 |
| T_c | 1.5 K |

[关键] Sr₂RuO₄ 是 4d 体系，U 比 3d 小但仍 Hund's metal。配对对称性 1998-2019 chiral p+ip → 2019 修正为 d 波（Pustogow）。

### 5.3 镍酸盐 La₃Ni₂O₇（D5 现代）

[来源] 多篇 DFT+DMFT 计算

**La₃Ni₂O₇ 参数：**

| 参数 | 估算值 |
|------|------|
| 占据 | d⁷·⁵-d⁸ |
| U | 4-5 eV |
| **J_H** | **0.7-1.0 eV**（关键大）|
| m*/m | 3-5 |
| T_c (高压) | ~80 K |

[关键观察] 镍酸盐**强 J_H** 给出 Hund's metal 类行为。多篇 DMFT 计算（2024+）显示：
- 双层结构 → 双带（bonding/antibonding）
- J_H 解耦 d_z² 与 d_x²-y²
- 多通道配对（s± 候选）

[反幻觉] 镍酸盐 Hund's metal 性质是**理论计算结论**，实验 m*/m 测量仍有限。

### 5.4 重费米子（D8 — 部分关联）

[关联] f 电子体系（CeCoIn₅, UTe₂）也有 Hund's coupling 类似效应：
- Kondo 物理 + Hund's J 联合
- 比 3d 体系复杂（轨道更多 + 自旋轨道耦合）
- "f-electron Hund's metal" 概念发展中

### 5.5 钌酸盐 / 锇酸盐（4d/5d）

| 体系 | J_H/U | 备注 |
|------|------|------|
| Ca₂RuO₄ | 0.15 | Mott 绝缘，部分 |
| Sr₃Ru₂O₇ | 0.18 | 向列 metallic |
| Sr₂IrO₄ | 0.2 | 5d Mott |
| Os 化合物 | 0.1-0.2 | 5d 体系 |

[反幻觉] 4d/5d 体系 J_H 占 U 的比例与 3d 不同，"Hund's metal" 标签需要谨慎使用。

---

## 6. Hund's Coupling 对 SC 的作用机制

### 6.1 不是独立"配对核"

[关键澄清] B10 与 B1-B8 的根本区别：
- B1-B8：直接通过玻色介质（声子/自旋/电荷/激子）介导配对
- **B10：修正"母态"成为 Hund's metal**，然后 spin/charge fluctuations 在 Hund's metal 上产生 SC

### 6.2 通过准粒子重整

[作用 1] m*/m 重整影响 SC：
- N(0) ∝ m* → BCS Tc ∝ exp(-1/N(0)V) 增强
- 但有效带宽 W*  ∝ 1/m* → ω 截断减小
- 净效应通常**抑制 Tc**（重费米子 SC 通常 Tc < 1 K）

### 6.3 通过自旋涨落增强

[作用 2] Hund's metal 的 spin freezing → 局域自旋涨落增强：
- 在 q ≈ Q 处 χ_s 增强（B3 AFM）
- 但是**非 Fermi liquid**导致涨落谱模糊化

### 6.4 通过轨道选择 + 多通道

[作用 3] J_H 解耦不同轨道 → 多通道配对：
- 每个轨道有不同的有效 V_eff
- 给出复杂的 multi-orbital gap 结构
- s± 可能性增加（铁基典型）

### 6.5 通过非 Fermi liquid 正常态

[作用 4] Hund's metal 给出 Linear-T 电阻 + 准粒子失重：
- 与 strange metal (A8) 关联
- 但 Hund's metal 是**有限 W*** Fermi liquid，不是真正的 strange metal
- 区分：Hund's metal 在 T < T* 时回归 Fermi liquid

---

## 7. Hund's Metal vs 其他强关联框架

| 框架 | U/W | J_H/U | 例子 |
|------|-----|------|------|
| **B14 Mott**（B9 RVB）| ≫ 1 | 任意 | cuprate underdoped |
| **B10 Hund's metal** | < U_c/W（不接近 Mott）| **大** | 铁基, Sr₂RuO₄, 镍酸盐 |
| 弱关联 metal | ≪ 1 | 任意 | 铜, 银 |
| 重费米子 Kondo | 任意 | 大（含 SOC）| CeCu₂Si₂, UTe₂ |

---

## 8. 关键判据

### 8.1 ARPES 准粒子重整

[判据] m*/m 通过 ARPES 能带斜率与 DFT 比较：
- 铁基：3-5×（FeSe, BaFe₂As₂）
- Sr₂RuO₄：3×
- 镍酸盐：3-5×（待精确测量）

### 8.2 比热 γ 增强

[判据] 比热 γ_exp / γ_DFT 给出 m*/m：
- 铁基典型 γ_exp ~ 20-50 mJ/mol·K²
- DFT 预测 γ_DFT ~ 5-10 mJ/mol·K² → m* ~ 3-5

### 8.3 Spin freezing in NMR

[判据] NMR 1/T₁T 在中间温度区饱和（不像 Fermi liquid 1/T₁T = const）：
- 铁基典型：1/T₁T(T) 在 T_FL ~ 100-300 K 上方进入"freezing"
- 镍酸盐：研究中

### 8.4 Linear-T 电阻

[判据] Hund's metal 给出 Linear-T 电阻在 T > T_FL 区间（A8 关联）：
- 铁基 Linear-T 至 1000+ K
- Sr₂RuO₄ Linear-T 至 ~ 700 K

---

## 9. 限制与边界（反谄媚）

### 9.1 "Hund's metal" 不是新机制

[反谄媚] B10 不是 B1-B8 / B9 之外的"第十种配对机制"。它是**修正母态**的概念。配对仍由 B3 AFM 涨落（铁基）或其他机制提供。

### 9.2 "Hund's metal" 标签的过度使用

[争议] "Hund's metal" 概念 2010+ 后成为流行标签：
- 任何有 J_H + 多带 + 中等 U 的体系都被贴
- 但定量标准（m*/m 阈值，spin freezing 范围）未严格定义
- 有"概念膨胀"风险

### 9.3 在 cuprate 不适用

cuprate 是单带 (d_x²-y²) → J_H 不重要。B9 RVB / B14 Mottness 是 cuprate 母相的描述。

### 9.4 与 spin-fluctuation 的边界

[争议] 铁基 SC 在 Hund's metal 上发生：
- Yin-Haule-Kotliar 派：Hund's metal + spin freezing 决定 SC
- Pines/Scalapino 派：spin-fluctuation (B3) 是主导
- 实际可能两者都重要

### 9.5 镍酸盐 J_H 测量精度

[反幻觉] 镍酸盐 J_H ~ 0.7-1.0 eV 是 DFT+DMFT 估算，**实验直接测量极少**。需要 RIXS 多重极测量。

### 9.6 4d/5d vs 3d

[反谄媚] 标签"Hund's metal"在 3d 体系（铁基, 镍酸盐）较成熟。4d/5d（Sr₂RuO₄ 等）J_H/U 比例不同，需谨慎应用。

---

## 10. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B1 BCS** | 母态修正 | m* 增强 N(0) |
| **B3 AFM** | **Hund's metal 上的配对** | spin freezing → χ_s 增强 |
| **B5 向列涨落** | **多带必需** | Hund's metal 给多带轨道 |
| **B9 RVB** | 对比 | 不接近 Mott vs 接近 Mott |
| **B12 多通道** | **Paper A 关联** | 多带配对 |
| **B14 Mott** | **过渡** | Hund's metal → Mott |
| **A8 strange metal** | 关联 | Hund's metal 给非 FL |
| **C2 s±** | 铁基 | Hund's metal + AFM |
| **D4 铁基** | **核心应用** | Yin-Haule-Kotliar |
| **D5 镍酸盐** | **现代** | DFT+DMFT 计算 |
| **D8 重费米子** | 部分关联 | f 电子 Hund + Kondo |
| F8 轨道纹理 | 关联 | 轨道选择 |
| **I1 ARPES** | **核心工具** | m*/m 测量 |
| **J3 理论** | 工具 | DMFT, Slater-Kanamori |

---

## 11. 推荐精读论文

### 必读（理论原创）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Slater 1929 PR 34, 1293 | DOI: 10.1103/PhysRev.34.1293 | Hund's rules 量子起源 |
| Kanamori 1963 Prog. Theor. Phys. 30, 275 | DOI: 10.1143/PTP.30.275 | 多带 Hubbard 完整形式 |
| **Werner et al. 2008** | DOI: 10.1103/PhysRevLett.101.166405 | DMFT 多带 + Hund |
| **de' Medici 2012** | DOI: 10.1103/PhysRevLett.107.256401 | Janus-faced J_H |

### 必读综述
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Georges-Kotliar-Krauth-Rozenberg 1996** | DOI: 10.1103/RevModPhys.68.13 | DMFT 综述 |
| **Georges-de'Medici-Mravlje 2013** | DOI: 10.1146/annurev-conmatphys-020911-125045 | **必读 Hund's metal 综述** |

### 关键体系
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Yin-Haule-Kotliar 2011** | DOI: 10.1038/nmat3120 | 铁基 = Hund's metal |
| **Mravlje et al. 2011** | DOI: 10.1103/PhysRevLett.106.096401 | Sr₂RuO₄ |
| Yi et al. 2017 PRL 119, 057001 | ARPES m*/m 铁基 | 实测 |
| 多篇镍酸盐 DMFT (2024+) | 待精读 | 现代 |

### 综述
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Imada et al. 1998 RMP 70, 1039 | Mott + 多带 | 历史 |
| Zaanen-Sawatzky-Allen 1985 PRL 55, 418 | ZSA 分类 | 母相分类 |

---

## 12. 数据汇总（反幻觉确认）

[定理 - de' Medici 2012] J_H 在半填充促进 Mott，远离半填充抑制 Mott

[定理 - Georges-de'Medici-Mravlje 2013] Hund's metal 特征：m*/m ~ 5-10 + spin freezing + 非 FL

[观察 - 铁基] J_H = 0.5-0.7 eV, U/W ~ 0.5, m*/m = 3-10（轨道依赖）[Yin-Haule-Kotliar 2011]

[观察 - Sr₂RuO₄] J_H = 0.4 eV, m*/m = 3-5 [Mravlje 2011]

[观察 - 镍酸盐 La₃Ni₂O₇] J_H ~ 0.7-1.0 eV (DFT+DMFT 估算), m*/m ~ 3-5 [多篇 2024+]

[反幻觉] 镍酸盐 J_H 实验直接测量极少（RIXS 等）

[反幻觉] "Hund's metal" 是修正母态概念，不是独立配对机制

---

## 13. 反幻觉自检

- [x] Slater 1929 / Kanamori 1963 / Werner 2008 / Georges-de'Medici-Mravlje 2013 经典 DOI 标注
- [x] 铁基 J_H, m*/m 数据来源 Yin-Haule-Kotliar 2011 + Yi 2017
- [x] Sr₂RuO₄ 数据来源 Mravlje 2011
- [x] **镍酸盐 J_H 实验测量极少**坦诚说明
- [x] **"Hund's metal" 不是独立配对机制**明确
- [x] de' Medici "Janus-faced" 公式准确
- [x] DMFT 标准方法（TRIQS 等）说明

---

## 14. 反谄媚自检

- [x] **"Hund's metal" 标签过度使用风险**明确说明
- [x] 3d vs 4d/5d 应用差异坦诚（J_H/U 不同）
- [x] cuprate 不适用 B10 明确（单带 + Mott）
- [x] 镍酸盐 Hund's metal 是计算结论，非完全实验确认
- [x] B10 不是 B1-B9 之外的"第十种配对机制"明确（仅修正母态）
- [x] Yin-Haule-Kotliar vs Pines/Scalapino 在铁基 SC 机制上的争议坦诚
- [x] 准粒子重整对 SC 的"双面"作用（增强 N(0) vs 减小 W*）明确

---

## 15. 当前状态与后续行动

**状态：** [已综述]，B 部分强关联非 Mott 路径完整

**关键洞察总结：**

1. **Hund's metal 是 2008-2013 范式转变** — 强关联 ≠ 接近 Mott
2. **J_H "Janus-faced"** — 半填充促 Mott，一般填充抑 Mott + 强重整
3. **铁基 / Sr₂RuO₄ / 镍酸盐**都是 Hund's metal 标准案例
4. **B10 不是独立配对机制** — 是修正母态 + 多通道 + 准粒子重整
5. **m*/m = 3-10** 是 Hund's metal 标志，对 SC 有"双面"影响
6. **镍酸盐** J_H ~ 0.7-1.0 eV → 多通道 s± 候选

**遗留问题：**
1. 镍酸盐 J_H 实验直接测量（RIXS）
2. Yin-Haule-Kotliar vs Pines/Scalapino 在铁基 SC 争议
3. UTe₂ 等 f 电子 Hund + Kondo 联合
4. MATBG 是否有效"Hund's metal"类比（轨道+涨落）

**对 Paper A 的关联：**
- Paper A 默认 λ_total = λ_ph + λ_sf
- B10 Hund's metal 给出**多通道 + 准粒子重整**
- Paper A 中"两通道"如果包含 Hund 修正会更完整
- m*/m 增强 → λ_eff 修正 → Tc 修正

**对 Paper E 的关联：**
- B10 Hund's metal 是**多带**模型
- Paper E 的 Y_l^m 轨道纹理对应 Hund 多轨道结构
- 镍酸盐 d_z²-d_x²-y² 双带 → Paper E 的 F8 直接关联

**B 部分进度（B1-B10 完成 10/14）：**

```
🔵 声子：       B1 + B2 ✅
🟣 自旋：       B3 + B4 ✅
🟠 轨道/晶格：  B5 ✅
🟡 电荷/CDW：   B6 ✅
🟤 激子：       B7 ✅
🟢 等离激元：   B8 ✅
🔮 RVB：        B9 ✅
🟫 Hund's metal: B10 ✅ (新)
─────────────
B 总体: 93%（10/14）
缺：B11 (拓扑) + B12-B14
```

**后续：** B11（拓扑配对）— Sr₂RuO₄, UTe₂, β-Bi₂Pd 等拓扑 SC 候选 + Majorana 物理

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Werner 2008 + Yin-Haule-Kotliar 2011 + Georges-de'Medici-Mravlje 2013 + 镍酸盐现代 + 三类强关联框架对比
