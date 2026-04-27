# B5. 向列涨落介导（NFMS — Nematic Fluctuations Mediated SC）

**MECE 编号：** B5
**关联 MECE：** B3（AFM 涨落对比）、B4（FM 涨落对比）、B12（多通道叠加 Paper A）、A8（Linear-T strange metal）、C1-C3（s/d/s± 都可被增强）、D4（铁基核心应用）、F8（轨道纹理）、H3（向列性 normal-state）、I7（弹光/弹性测量）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Fradkin 2010 RMP + Fernandes 2014 综述 + Lederer 2015 + Romero 2026 已精读）

---

## 1. 物理定义与核心思想

**向列涨落（Nematic Fluctuations）：** 当材料接近**向列量子临界点**（Nematic QCP）时，C₄ → C₂ 旋转对称性破缺的涨落 ψ_n 增强。这种涨落作为玻色介质介导电子配对。

[关键观察]
- 向列序参量 ψ_n 是**轨道/晶格自由度**的，**不**直接耦合自旋
- 因此向列涨落保持 **spin-singlet**（与 B4 FM 形成 spin-triplet 完全不同）
- **核心特点：** 向列涨落对**所有**配对通道（s, s±, d）都增强 — 不像 AFM 偏好 d 波

[Lederer 2015 关键定理]
> 在向列 QCP 处，所有 SC 通道的 Tc 都被增强；但增强幅度和饱和效应取决于 BCS 通道与 nematic 涨落的耦合细节。

[来源] Lederer et al. 2015 PRL 114, 097001 [DOI: 10.1103/PhysRevLett.114.097001]

> **物理图像：** 向列涨落是"对称性破缺的迟早"，给所有对的电子提供"轨道扭曲背景"，让所有配对都更容易。这与 AFM/FM 的"自旋背景"完全不同。

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1998 | Kivelson-Fradkin-Emery 提出 cuprate 向列概念 | Nature 393, 550 |
| 2007 | Sr₃Ru₂O₇ 向列态发现 | Borzi et al. Science 315, 214 |
| 2009 | 铁基 SC 向列序 / 涨落识别 | 多篇 |
| **2010** | **Fradkin-Kivelson-Lawler-Eisenstein-Mackenzie RMP 82, 1225** | **必读综述** |
| 2010 | Chu et al. 弹光实验定量化向列 | Science 329, 824 |
| 2011 | Fernandes 系统化向列 vs spin 涨落理论 | Nat. Phys. 7, 729 |
| 2014 | Böhmer 等弹性常数软化 | PRL 112, 047001 |
| **2014** | **Fernandes-Chubukov-Schmalian** 综述 | Nat. Phys. 10, 97 |
| **2015** | **Lederer-Schattner-Berg-Kivelson** 向列 QCP 配对增强 | PRL 114, 097001 |
| 2017 | Worasaran et al. 应变调向列 | Science 357, 75 |
| **2026** | **Romero/Armitage** FTS 双 Planckian 通道 | Nat. Phys. arXiv:2505.00623（已精读）|

---

## 3. 数学框架

### 3.1 向列序参量

[定义] 标量向列序参量（Ising-向列）：
$$\psi_n \propto \sum_{\mathbf{k}} f_n(\mathbf{k})\, \langle c^{\dagger}_{\mathbf{k}\sigma} c_{\mathbf{k}\sigma}\rangle$$

其中 f_n(k) 是 d_x²-y² 形式的 form factor（即在 k_x 和 k_y 方向有不同符号）。

[物理] 当 ψ_n ≠ 0：
- 晶格在 a/b 方向不再等价（C₄ → C₂）
- 轨道 d_xz / d_yz 占据数不同
- 弹性常数 c₆₆ → 0 软化

### 3.2 向列极化率

[定义] 向列响应函数：
$$\chi_n(\mathbf{q}, \omega) = -i \int dt\, \theta(t) e^{i\omega t} \langle [\psi_n(\mathbf{q}, t), \psi_n(-\mathbf{q}, 0)]\rangle$$

向列 QCP 处 χ_n(0, 0) 发散：
$$\chi_n(\mathbf{q}, \omega) = \frac{\chi_0}{r + c|\mathbf{q}|^2 - i\omega/\Gamma}$$

其中 r → 0 处 QCP 发生。

### 3.3 配对核

[定义] 向列涨落配对核（singlet 通道）：
$$V_{\text{nem}}(\mathbf{k}, \mathbf{k}') = -|g_n|^2 f_n(\mathbf{k}) f_n(\mathbf{k}') \chi_n(\mathbf{k} - \mathbf{k}', 0)$$

其中 g_n 是电子-向列耦合常数。

[关键差异 vs AFM/FM]
- **AFM** χ_s 在 q ≈ Q 处增强 → q-dependent 配对核
- **FM** χ_s 在 q ≈ 0 处增强 → 但只对 spin-triplet
- **向列** χ_n 在 q ≈ 0 处增强 → spin-singlet 通道，但**form factor f_n(k) 起关键作用**

### 3.4 form factor 决定增强对称性

[定理 - Maier-Scalapino 2014] 向列涨落主要增强**与 form factor 同对称性**的配对通道：
- f_n ~ d_x²-y² → 增强 d_x²-y² 配对（cuprate 风格）
- f_n ~ s+ → 增强 s 波配对（铁基风格）

[来源] Maier-Scalapino 2014 PRB 90, 174510

---

## 4. 与 B3/B4 的关键对比

| 维度 | B3 AFM | B4 FM | **B5 Nematic** |
|------|--------|-------|----------------|
| **q 增强** | q ≈ Q | q ≈ 0 | q ≈ 0（与 FM 类似）|
| **耦合对象** | 自旋 | 自旋 | **轨道/晶格** |
| **配对自旋态** | singlet | **triplet** | **singlet** |
| **配对对称性** | d_x²-y² 自然 | p/f 波 | **同 form factor 对称性** |
| **Tc 增强通道** | 选择性（d 波偏好）| 选择性（triplet）| **多通道（取决耦合）** |
| **与 AFM 共存** | — | 互斥 | **共存增强**（铁基典型）|
| **C₄ 破缺** | 无 | 无 | **是** |

[关键洞察] B5 是 B3/B4 的"互补伙伴" — 在铁基 SC 中向列涨落 + AFM 涨落往往**协同**增强配对，而不互相抑制。

---

## 5. 关键判据

### 5.1 弹性常数 c₆₆ 软化

[关键判据] 接近向列 QCP 时，弹性常数 c₆₆ → 0：
$$c_{66}(T) = c_{66}^{\text{bare}} - \lambda^2 \chi_n(T)$$

[案例]
- BaFe₂(As,P)₂：c₆₆ 在 T_s 附近软化 ~ 70%
- FeSe：极强弹性软化（无磁性 + 强向列）
- Sr₃Ru₂O₇：场致向列软化

[来源] Böhmer et al. 2014 PRL 112, 047001

### 5.2 弹光（弹性应变响应）

[关键判据] 应变 ε 诱导 ψ_n：
$$\frac{\partial \rho_a - \rho_b}{\partial \varepsilon} \sim \chi_n(0, 0)$$

[案例] Chu et al. 2010 Science 329, 824 在 BaFe₂(As,P)₂ 测量到大向列响应。

### 5.3 共形电阻各向异性 ρ_a/ρ_b

[判据] 向列态下 ρ_a ≠ ρ_b（典型差 10-30%）。

### 5.4 ARPES 能带分裂

[判据] d_xz / d_yz 能带在向列态下分裂（轨道排序）。

---

## 6. 关键家族数据

### 6.1 铁基（D4 — 标准应用）

[来源] Fernandes-Chubukov-Schmalian 2014 Nat. Phys. 10, 97 [DOI: 10.1038/nphys2877]

| 材料 | T_s (K) | T_N (K) | T_c 最大 (K) | 向列特征 |
|------|---------|---------|------------|---------|
| LaFeAsO | 156 | 138 | 26 (F 掺) | T_s > T_N（向列先于磁）|
| BaFe₂As₂ | 138 | 138 | 22 (Co 掺) | T_s = T_N（混合）|
| BaFe₂(As,P)₂ | — | — | 30 | 向列 QCP @ x ≈ 0.30 |
| **FeSe** | 90 | — | 8.5（常压）| **无磁性，纯向列**（特殊）|
| **FeSe/STO** | — | — | ~65? | 向列 + 界面增强 |

[关键特点] BaFe₂(As,P)₂ 在 P 掺杂调控下经过向列 QCP，Tc 在 QCP 附近达到峰值（~30 K）。

### 6.2 Sr₃Ru₂O₇（典型场致向列）

[来源] Borzi et al. 2007 Science 315, 214

在 ~ 8 T 场下出现"meta-magnetic"向列态：
- 电阻各向异性 ~ 100%
- 可能与 metamagnetic QCP 关联
- 是非铁基中最典型的向列 SC 候选

### 6.3 铜氧化物（D3 — 部分关联）

[争议] cuprate 中向列性是否独立于 CDW / spin / pseudogap 仍存争议。

[案例]
- YBCO underdoped：扭曲 ABO 应力 → 向列响应
- Bi-2212：STM 局部向列
- 但与 CDW / PDW 强耦合

[来源] Achkar et al. 2016 Science 351, 576

### 6.4 重费米子（D8 — 部分关联）

| 材料 | 向列特征 |
|------|---------|
| URu₂Si₂ | "hidden order" 包含向列分量 |
| YbRh₂Si₂ | metamagnetic + 向列候选 |

### 6.5 FeTe₁₋ₓSeₓ — Romero 2026 关联

[来源] Romero/Armitage 2026 Nat. Phys. arXiv:2505.00623（**已精读**）

[已知] FeTeSe 高能段 Planckian (α ≈ 3) + 低能段 Planckian (α ≈ 1)，提示**双通道**输运。

[反幻觉] Romero 论文未明确把双 Planckian 归因于"AFM + 向列"两个通道。文献中标记为"two-channel parallel conduction"，机制论是开放问题。

[反谄媚] **Paper A 中已警告：Romero 双通道 ≠ Paper A 双通道**。FTS 中向列涨落是否是其中一个通道仍待确认。

### 6.6 镍酸盐（D5 — 待研究）

向列性在镍酸盐中是否存在仍是开放问题。理论上双层结构 + Hund 多轨道 → 可能有向列分量。

---

## 7. 限制与边界（反谄媚）

[反谄媚] 必须明确：

### 7.1 向列 vs 自旋涨落的区分困难

- 在铁基中 T_s 与 T_N 接近 → 向列与磁性涨落耦合
- 实验上区分两个通道需要**应变控制**（Chu 2010 弹光技术）+ **同位素**（B4 等）
- 单纯输运 / 比热不足以判定向列贡献

### 7.2 向列涨落是否真的"主导"配对

[争议] FeSe 是"无磁性 + 强向列"的最纯案例，Tc=8.5 K（常压）。但：
- 增强不显著（铁基典型 Tc=20-30 K，FeSe 反而 < 10 K）
- 暗示向列涨落作为单独通道**不强**
- FeSe/STO Tc=65 K 可能涉及界面声子 + 向列联合（B12 多通道）

### 7.3 与 BCS/Eliashberg 数学结构相同

[反谄媚] 向列机制不是新数学，仍是 BCS 自洽方程框架。新东西是**配对核 V_eff 的具体形式**。

### 7.4 缺乏 ab initio 框架

类比 B3/B4：χ_n(q, ω) 难第一性原理计算。多用 RPA + 唯象。DFT + 应变响应是替代但不全面。

### 7.5 普适比（无 ω_res 类型普适数）

[未检验] 与 B3 的 ω_res/k_BTc ≈ 5 不同，向列涨落没有类似的普适数。这使诊断更困难。

### 7.6 与 CDW / 拓扑 / Mottness 重叠

向列性常与 CDW、轨道选择 Mott、PDW 等竞争或共存。单纯归因困难。

---

## 8. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B3 AFM** | **共存伙伴** | 铁基中协同增强 |
| **B4 FM** | 对比 | 自旋 vs 轨道/晶格 |
| **B12 多通道** | **核心组分** | Paper A 中可能的额外通道 |
| **C1 s 波** | 增强 | 取决 form factor |
| **C2 s±** | 铁基应用 | 增强与 AFM 共存 |
| **C3 d 波** | 增强 | 与 cuprate AFM 共存 |
| **A8 strange metal** | **Romero 2026** | Linear-T 双通道（待确认是否向列）|
| **D4 铁基** | **核心应用** | BaFe₂(As,P)₂ QCP, FeSe 纯向列 |
| **D5 镍酸盐** | 待研究 | 多轨道 → 可能向列 |
| **F8 轨道纹理** | **直接关联** | Paper E |
| H3 向列正常态 | 同源 | normal-state 向列 |
| H4 CDW | 重叠/竞争 | cuprate 中纠缠 |
| I7 弹光/弹性 | **核心工具** | Chu 2010, Böhmer 2014 |

---

## 9. 推荐精读论文

### 必读（综述）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Fradkin et al. 2010 RMP 82, 1225** | DOI: 10.1103/RevModPhys.82.1225 | **必读综述** |
| **Fernandes-Chubukov-Schmalian 2014** | DOI: 10.1038/nphys2877 | 铁基向列综述 |
| Vojta 2009 综述 | Adv. Phys. 58, 699 | 一般 nematic |

### 关键理论
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Lederer et al. 2015** | DOI: 10.1103/PhysRevLett.114.097001 | QCP 配对增强 |
| Maier-Scalapino 2014 | DOI: 10.1103/PhysRevB.90.174510 | form factor 选择性 |
| Fernandes 2011 Nat. Phys. 7, 729 | nematic vs spin | 待精读 |

### 关键实验
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Chu et al. 2010 | DOI: 10.1126/science.1190482 | 铁基弹光 |
| Borzi et al. 2007 | DOI: 10.1126/science.1134796 | Sr₃Ru₂O₇ |
| Böhmer et al. 2014 PRL 112, 047001 | DOI: 10.1103/PhysRevLett.112.047001 | 弹性软化 |
| **Romero/Armitage 2026** | arXiv:2505.00623 | **FTS Planckian 双通道**（已精读）|

### 现代关键
| 论文 | DOI/来源 | 状态 |
|------|---------|------|
| Worasaran et al. 2017 Science 357, 75 | 应变调向列 | 待精读 |
| Achkar et al. 2016 Science 351, 576 | YBCO 向列 | 待精读 |

---

## 10. 数据汇总（反幻觉确认）

[定理 - Lederer 2015] 向列 QCP 处所有 SC 通道 Tc 增强；增强幅度依赖 BCS 通道与 nematic 涨落耦合细节

[定理 - Maier-Scalapino 2014] 向列涨落主要增强与 form factor f_n(k) 同对称性的配对通道

[观察] BaFe₂(As,P)₂ Tc 在向列 QCP（x ≈ 0.30）附近达到峰值 ~30 K [Fernandes 2014 综述]

[观察] FeSe 是"无磁性+强向列"特殊案例，Tc=8.5 K（常压）[多篇]

[观察 - Chu 2010] BaFe₂As₂ 弹光响应 ~ Curie-Weiss 型 → 向列涨落证据

[观察 - Böhmer 2014] BaFe₂(As,P)₂ c₆₆ 软化 ~70%

[反幻觉] Romero 2026 双通道未明确归因向列。**Paper A 已警告"两通道≠两通道"**。

---

## 11. 反幻觉自检

- [x] Fradkin 2010 RMP / Fernandes 2014 / Lederer 2015 经典 DOI 标注
- [x] BaFe₂(As,P)₂ Tc 峰值与 QCP 关联 → 来源 Fernandes 2014 综述
- [x] FeSe 数据"无磁性+强向列"特殊性明确说明
- [x] **Romero 2026 双通道**未归因向列（未做 OverClaim）
- [x] Sr₃Ru₂O₇ 场致向列来源 Borzi 2007
- [x] 弹光数据来源 Chu 2010 Science 329, 824
- [x] form factor 选择性 → 来源 Maier-Scalapino 2014

---

## 12. 反谄媚自检

- [x] **向列涨落作为单独通道不强**（FeSe 仅 8.5 K）— 坦诚说明
- [x] 向列 vs 自旋涨落区分困难（应变 + 同位素必需）
- [x] 没有类似 ω_res/k_BTc ≈ 5 的普适数 — 诊断更困难
- [x] **Paper A 警告"两通道≠两通道"** — Romero 2026 不能直接归因向列
- [x] FeSe/STO Tc=65 K 是多通道（界面声子+向列）联合，不能单纯归功向列
- [x] 缺乏 ab initio 框架明确（χ_n 难第一性原理计算）
- [x] 不夸大 cuprate 向列贡献（与 CDW/PDW/pseudogap 难分离）

---

## 13. 当前状态与后续行动

**状态：** [已综述]，B 部分非声子通道齐备（B3 AFM + B4 FM + B5 Nematic）

**关键洞察总结：**

1. **B5 是 B3/B4 的"轨道兄弟"**：q≈0 + spin-singlet + form factor 选择性
2. **铁基中 B3 + B5 协同增强**（FeSe/STO Tc=65 K 是关键案例）
3. **FeSe 纯向列不强** → 向列单独通道不足以高 Tc
4. **Romero 2026 FTS 双通道**仍是开放机制题（不归因向列）
5. **铜氧 / 镍酸盐 / 重费米子向列性**仍是研究前沿

**遗留问题：**
1. Romero 2026 双通道的精确归因（向列 vs AFM vs CDW）
2. 镍酸盐多轨道结构是否含向列分量
3. cuprate 向列与 CDW/PDW 的精确分离
4. FeSe/STO Tc=65 K 的多通道权重（声子 + 向列 + AFM）

**对 Paper A 的关联：**
- Paper A 默认 λ_total = λ_ph + λ_sf（AFM 通道）
- **B5 向列通道 λ_nem 未明确**，是 Paper A 潜在扩展
- FTS Romero 2026 双通道**不直接**支持 Paper A 框架（"两通道≠两通道"）

**对 Paper E 的关联：**
- Paper E 的 F8 轨道纹理 ↔ B5 form factor f_n(k) 高度对应
- 向列涨落本质上是**轨道占据涨落**，与 Paper E 的轨道-能隙原则共生
- 但 Paper E 默认 spin-singlet，与 B5 兼容（不像 B4）

**B 部分总结（B1-B5 完成 5/14）：**

```
已完成机制四类：
- 声子机制：B1 BCS + B2 Eliashberg ✅
- 自旋通道：B3 AFM + B4 FM ✅
- 轨道/晶格通道：B5 Nematic ✅
─────────────
缺：B6-B11（电荷/激子/磁子/双磁子/掺杂等）+ B12 多通道 + B13 平坦带 + B14 Mottness
```

**后续：** B 部分主流通道完成。建议下一篇 B6（电荷涨落）或 B12（多通道叠加 — Paper A 直接相关）。

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Fradkin RMP + Fernandes 综述 + Lederer 2015 + Romero 2026 关联 + Paper A 多通道警告
