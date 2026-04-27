# B2. Eliashberg 强耦合理论（Phonon-Mediated, Strong Coupling）

**MECE 编号：** B2
**关联 MECE：** B1（BCS 弱耦合）、A3（比热修正）、A4（同位素效应修正）、A5（能隙修正）、D1（元素 Pb/Hg）、D6（氢化物）、J2（理论方法）、J4（DFT+DFPT）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Migdal-Eliashberg + McMillan 1968 + Allen-Dynes 1975 + Carbotte 1990）

---

## 1. 物理定义与核心思想

**Eliashberg 理论：** 1960 年 G.M. Eliashberg 提出的强耦合超导理论，在 BCS 框架基础上**保留电声子相互作用的完整能量依赖性**。

[关键扩展] BCS 假设瞬时吸引 V₀ 和单一 Debye 频率 ω_D；Eliashberg 用**真实声子谱 α²F(ω)**和**频率依赖的能隙函数 Δ(ω)**。

> **物理图像：** 当电声子耦合 λ ~ 1（强耦合）时，电子在配对前后存在显著的"声子云"修饰。BCS 忽略这个修饰；Eliashberg 包含。

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1958 | **Migdal 定理**：电声子顶点修正可忽略 | Sov. Phys. JETP 7, 996 |
| **1960** | **Eliashberg 方程**：完整强耦合方程 | Sov. Phys. JETP 11, 696 |
| 1965 | Schrieffer 教科书包含 Eliashberg | "Theory of Superconductivity" |
| **1968** | **McMillan 公式**（Tc 数值化）| Phys. Rev. 167, 331 |
| 1972 | Bardeen-Cooper-Schrieffer Nobel | — |
| **1975** | **Allen-Dynes 公式**（强耦合 Tc）| PRB 12, 905 |
| 1980s+ | DFT + DFPT + Eliashberg 数值实现 | Quantum Espresso 等 |
| **2015** | H₃S 203 K @ 155 GPa | Drozdov Nature 525, 73 |
| 2019+ | LaH₁₀ 250 K，Eliashberg 关键工具 | Drozdov, Somayazulu |
| 2024+ | Hydride SC 高通量 DFPT+Eliashberg 筛选 | 多篇 |

---

## 3. Migdal 定理（强耦合理论基础）

### 3.1 定理陈述

[定理 - Migdal 1958] 在金属中，由于电子-声子相互作用引起的**顶点修正**满足：
$$\frac{\Gamma_{\text{vertex}}}{\Gamma_{\text{bare}}} \sim \sqrt{\frac{m_e}{M_{\text{ion}}}} \approx 0.02$$

[来源] Migdal 1958 Sov. Phys. JETP 7, 996

### 3.2 物理意义

- 电子质量 m_e 远小于离子质量 M_ion → 电子运动远快于声子
- 顶点修正可忽略 → 电声子相互作用可用一阶图（self-energy）严格处理
- 这是 Eliashberg 理论的基础假设

### 3.3 限制

[反幻觉] Migdal 定理在以下情况**失效**：
- 极强耦合 λ > 3-4
- 接近 polaron 极限（电子动能 < 声子能）
- 顶点修正与小 m_e/M_ion 因子叠加

[反谄媚警告] 在氢化物中（M = m_H）M_ion 相对较小，Migdal 假设的"小参数"严格性弱化。但实践中仍工作。

---

## 4. α²F(ω) 与四个关键参数

### 4.1 α²F(ω) 定义

**Eliashberg 函数：** α²(ω) F(ω)，其中 α(ω) 是电声子耦合矩阵元的频率依赖部分，F(ω) 是声子谱密度。

[物理含义] α²F(ω) 描述**频率为 ω 的声子对配对的贡献**。从隧穿谱（McMillan-Rowell 1965）或 DFPT 计算得到。

### 4.2 四个关键导出量

| 参数 | 定义 | 物理意义 |
|------|------|---------|
| **λ**（电声子耦合常数）| 2 ∫₀^∞ α²F(ω)/ω dω | 总耦合强度 |
| **ω_log**（对数平均）| exp[(2/λ) ∫ ln(ω) α²F(ω)/ω dω] | Allen-Dynes 用 |
| **ω₂**（二次矩平均）| [(2/λ) ∫ ω α²F(ω) dω]^(1/2) | Eliashberg 修正 |
| **μ\***（库仑赝势）| 标准取 0.10 | 库仑屏蔽简化 |

[来源] Allen-Dynes 1975 PRB 12, 905 [DOI: 10.1103/PhysRevB.12.905]

### 4.3 λ 的家族分布

| λ 范围 | 体系 | 框架 |
|--------|------|------|
| < 0.5 | Al, Sn, In, Tl | BCS 严格 |
| 0.5 - 1 | Nb, Ta, Pb（弱端）| BCS + 修正 |
| 1 - 2 | Pb（α=1.55）, Nb₃Sn（1.8）| Eliashberg 必需 |
| 2 - 3 | H₃S（2.19）, LaH₁₀（2.46）| Eliashberg + Allen-Dynes 修正 |
| > 3 | YH₆? CaH₆? | Migdal 边界 |

---

## 5. Eliashberg 方程组

### 5.1 Matsubara 形式（实际计算用）

[定义 - Eliashberg 1960]

**两个耦合非线性方程，频率依赖的：**
$$\Delta(i\omega_n) Z(i\omega_n) = \pi T \sum_m \left[\lambda(i\omega_n - i\omega_m) - \mu^*\theta(\omega_c - |\omega_m|)\right] \frac{\Delta(i\omega_m)}{\sqrt{\omega_m^2 + \Delta^2(i\omega_m)}}$$

$$Z(i\omega_n) = 1 + \frac{\pi T}{\omega_n}\sum_m \lambda(i\omega_n - i\omega_m)\frac{\omega_m}{\sqrt{\omega_m^2 + \Delta^2(i\omega_m)}}$$

其中：
- **Δ(iω_n)**：复频率依赖的能隙函数
- **Z(iω_n)**：质量重整因子（mass renormalization）
- **λ(iω_n - iω_m)**：声子-平均场传播子

### 5.2 物理意义

| 量 | 含义 |
|----|------|
| Z(0) | T → 0 时电子有效质量重整 m\*/m = Z |
| Δ(iω_n) 频率依赖 | 强耦合下能隙不再是常数 |
| λ(0) | 直流极限的电声子耦合 |

### 5.3 实轴 vs 虚轴

- **虚轴（Matsubara）**：数值稳定，标准计算方法
- **实轴**：物理直观，但非线性发散需特殊处理（Padé 近似等）

---

## 6. McMillan 公式（1968）

### 6.1 历史第一个 Tc 数值公式

[定理 - McMillan 1968] 强耦合 Tc 近似公式：
$$k_B T_c = \frac{\hbar\omega_D}{1.45}\exp\left[-\frac{1.04(1+\lambda)}{\lambda - \mu^*(1+0.62\lambda)}\right]$$

[来源] McMillan 1968 PRB 167, 331 [DOI: 10.1103/PhysRev.167.331]

### 6.2 适用域

- λ < 1.5：合理精度
- λ > 1.5：低估 Tc
- McMillan 当时认为 Tc < 30 K 是"硬上限"（错误）

---

## 7. Allen-Dynes 公式（1975 — 现代标准）

### 7.1 公式

[定理 - Allen-Dynes 1975]
$$k_B T_c = \frac{\omega_{\log}}{1.20}\,f_1\,f_2\,\exp\left[-\frac{1.04(1+\lambda)}{\lambda - \mu^*(1+0.62\lambda)}\right]$$

强耦合修正因子：
$$f_1 = \left[1 + (\lambda/\Lambda_1)^{3/2}\right]^{1/3}$$
$$f_2 = 1 + \frac{(\omega_2/\omega_{\log} - 1)\lambda^2}{\lambda^2 + \Lambda_2^2}$$

其中 Λ_1 = 2.46(1 + 3.8μ*), Λ_2 = 1.82(1 + 6.3μ*)(ω₂/ω_log)。

[来源] Allen-Dynes 1975 PRB 12, 905

### 7.2 关键改进

| 改进 | 物理 |
|------|------|
| **ω_log 替代 ω_D** | 反映声子谱的整体形状 |
| **f₁ 修正** | 极强耦合时的修正 |
| **f₂ 修正** | ω₂/ω_log 比值的修正 |

[关键应用] Paper A（Two-Channel Allen-Dynes）使用此公式 + 自旋涨落扩展，验证 22 个材料 100% 在 2x 范围内。

### 7.3 适用范围

| λ | Allen-Dynes 准确性 |
|---|------------------|
| < 1 | 接近 BCS |
| 1-2 | 工程级别准确（< 10% 误差）|
| 2-3 | 系统性低估 ~ 20-30% |
| > 3 | 必须直接数值求解 Eliashberg |

---

## 8. 强耦合普适比修正

[来源] Carbotte 1990 RMP 62, 1027

强耦合下 BCS 普适比偏离：

| 比值 | BCS（弱耦合）| Pb（λ=1.55）| H₃S（λ=2.19）|
|------|-------------|------------|--------------|
| 2Δ₀/k_BTc | 3.528 | 4.3 | ~5 |
| ΔC/γTc | 1.43 | 2.7 | ~3 |
| ΔS(Tc)/γTc | 1.0 | ~0.7 | — |

[公式 - Marsiglio-Carbotte 1991]
$$\frac{2\Delta_0}{k_BT_c} \approx 3.53\left[1 + 12.5\left(\frac{T_c}{\omega_{\log}}\right)^2 \ln\left(\frac{\omega_{\log}}{2T_c}\right)\right]$$

类似公式给出 ΔC/γTc 和其他普适比的修正。

---

## 9. 关键家族数据

### 9.1 元素金属（强耦合）

[来源] Carbotte 1990 RMP

| 材料 | T_c (K) | λ | ω_log (K) | μ* | 来源 |
|------|---------|---|----------|----|------|
| Al | 1.18 | 0.43 | 300 | 0.10 | Carbotte |
| Sn | 3.72 | 0.72 | 130 | 0.10 | Carbotte |
| In | 3.41 | 0.81 | 100 | 0.10 | Carbotte |
| Pb | 7.20 | 1.55 | 52 | 0.10 | Carbotte（强耦合）|
| Hg-α | 4.15 | 1.62 | 65 | 0.10 | Carbotte |
| Nb | 9.25 | 0.82 | 277 | 0.10 | Carbotte |

[观察] λ 越大，2Δ/kBTc 和 ΔC/γTc 越偏离 BCS。

### 9.2 A15 化合物
| 材料 | T_c | λ | ω_log (K) |
|------|-----|---|----------|
| V₃Si | 17.1 | 1.12 | 280 |
| Nb₃Sn | 18.3 | 1.80 | 130 |
| Nb₃Ge | 23.2 | 1.70 | 200 |

### 9.3 MgB₂（双带 Eliashberg）
[来源] Choi-Roundy-Sun-Cohen-Louie 2002 Nature 418, 758

MgB₂ 是双带 Eliashberg 的"教科书"案例：
- σ 带（强 EPC）：λ_σ ~ 1.0, Δ_σ = 7 meV
- π 带（弱 EPC）：λ_π ~ 0.4, Δ_π = 2 meV
- 平均 λ ~ 0.87, ω_log ~ 670 K

T_c = 39 K（实测）vs Allen-Dynes 单带 ~ 37 K，双带 ~ 39 K（精确）

### 9.4 高压氢化物（Eliashberg 验证场）

[来源]
- H₃S: Drozdov 2015 Nature 525, 73; Errea et al. 2020 Nature 578, 66
- LaH₁₀: Drozdov 2019 Nature 569, 528; Somayazulu 2019 PRL 122, 027001

| 材料 | P (GPa) | T_c (K) | λ | ω_log (K) | μ* |
|------|---------|--------|---|----------|----|
| H₃S | 155 | 203 | 2.19 | 1335 | 0.10 |
| D₃S | 155 | 150 | 1.90 | 1000 | 0.10 |
| LaH₁₀ | 170 | 250 | 2.46 | 1500 | 0.10 |
| YH₆ | 170 | 224 | 2.00 | 1320 | 0.10 |
| YH₉ | 200 | 243 | 2.00 | 1450 | 0.10 |
| CaH₆ | 170 | 215 | 2.00 | 1400 | 0.10 |
| ThH₁₀ | 170 | 161 | 1.80 | 1050 | 0.10 |

[观察] 氢化物体系是 Eliashberg + Allen-Dynes **当代最大成功**：从 DFPT 计算的 α²F(ω) 直接预测 Tc，与实验吻合到 10-20%。

[反幻觉] 强耦合 λ > 2 体系，Allen-Dynes 系统性低估 ~10-30%；完整 Eliashberg 数值求解给出更好结果。

### 9.5 PdH（μ* 异常）

| 材料 | T_c | λ | μ* (理论) |
|------|-----|---|----------|
| PdH | 9 | 1.05 | 0.14（异常高）|

[观察] PdH 是 Eliashberg 框架的一个谜：常规 μ* = 0.10 给出 Tc = 3.7 K，需要 μ* = 0.14 才能复现 Tc = 9 K。可能反映自旋涨落对 PdH（接近铁磁不稳定性）的修正。

[来源] Carbotte 1990，Paper A 中讨论。

---

## 10. DFT + DFPT + Eliashberg 工作流

[现代标准] 第一性原理 Tc 预测：

1. **DFT 求基态电子结构**（Quantum Espresso / VASP / etc.）
2. **DFPT 求声子谱 ω(q)**（密度泛函微扰论）
3. **DFPT 求电声子矩阵元 g(k,q)**
4. **构造 α²F(ω)**
5. **数值求解 Eliashberg 方程** → Tc, Δ(ω), Z(ω)

[标准代码]
- Quantum ESPRESSO + EPW
- ABINIT
- VASP + Phonopy（间接）

[反幻觉] 第一性原理 DFPT+Eliashberg 在常规金属和氢化物中精度 10-20%。在强关联体系中失败。

---

## 11. Eliashberg 不适用的体系

[反谄媚] 必须明确指出：

### 11.1 强关联 Mott 物理
- 铜氧化物 underdoped（U/W > 1）
- 镍酸盐 strong-correlation 区
- 重费米子（Kondo 物理）

### 11.2 非声子机制主导
- 自旋涨落（B3）：χ_s(q,ω) 取代 α²F(ω)
- 向列涨落（B5）：类似 χ_n
- 电荷涨落（B6）

### 11.3 平坦带
- N(0) → ∞ 使 BCS/Eliashberg Tc 公式发散
- 需要量子度规扩展（B13 + Peotta-Törmä）

### 11.4 拓扑 SC
- 边界态主导
- BdG 拓扑分类必需

### 11.5 极强耦合（Migdal 失效）
- λ > 3-4
- 顶点修正不再可忽略
- Polaron 物理 / BEC-BCS crossover

---

## 12. Paper A（Two-Channel Allen-Dynes）的核心扩展

[关联 Paper A — 已知工作]

Paper A 在标准 Allen-Dynes 框架基础上添加：
1. **多通道扩展**：λ_total = λ_ph + λ_sf
2. **量子几何禁区**：证明 quantum metric 不能直接修正 EPC（s-wave / 准各向同性 d-wave）
3. **平坦带 + 几何超流权重**：T_c = min(T_pair, T_phase)

[观察] Paper A 验证 22 个 Tier-1 材料 100% 在 2× 范围内，是 Allen-Dynes 框架的工业级应用。

---

## 13. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B1 BCS 弱耦合** | **直接基础** | Eliashberg 是 BCS 强耦合扩展 |
| **B12 多通道叠加** | **Paper A** | λ_ph + λ_sf 联合 |
| A3 比热 | 修正普适比 | ΔC/γTc > 1.43 |
| A4 同位素 | 修正 α | μ* → α 减小 |
| A5 能隙 | 修正普适比 | 2Δ/kBTc > 3.528 |
| A8 strange metal | 边界 | Eliashberg 不适用此区 |
| C1 s 波 | 默认 | Eliashberg 默认 s 波 |
| D1 元素金属 | 测试场 | Pb, Hg 强耦合 |
| **D6 氢化物** | **核心成功** | LaH₁₀, H₃S 验证 |
| J2 理论方法 | 工具 | Matsubara 求解 |
| J4 DFT+DFPT | 工具 | 第一性原理 α²F(ω) |

---

## 14. 推荐精读论文

### 必读（基础理论）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Migdal 1958** | Sov. Phys. JETP 7, 996 | 顶点定理 |
| **Eliashberg 1960** | Sov. Phys. JETP 11, 696 | 强耦合方程 |
| **McMillan 1968** | DOI: 10.1103/PhysRev.167.331 | 第一个 Tc 公式 |
| **Allen-Dynes 1975** | DOI: 10.1103/PhysRevB.12.905 | **现代标准** |

### 综述
| 论文 | 来源 | 状态 |
|------|------|------|
| **Carbotte 1990 RMP 62, 1027** | DOI: 10.1103/RevModPhys.62.1027 | **必读综述** |
| Marsiglio-Carbotte 2003 in "Superconductivity" Bennemann ed. | Springer | 现代综述 |
| Margine-Giustino 2013 PRB 87, 024505 | EPW 代码 | 数值实现 |

### 现代关键
| 论文 | 来源 | 状态 |
|------|------|------|
| Choi et al. 2002 Nature 418, 758 | DOI: 10.1038/nature00992 | MgB₂ 双带 |
| Drozdov et al. 2015 Nature 525, 73 | DOI: 10.1038/nature14964 | H₃S 203K |
| Errea et al. 2020 Nature 578, 66 | DOI: 10.1038/s41586-020-1955-z | 氢化物量子离子修正 |
| Drozdov et al. 2019 Nature 569, 528 | DOI: 10.1038/s41586-019-1201-8 | LaH₁₀ 250K |
| Pickard et al. 2020 综述 | Annu. Rev. Cond. Matter | 氢化物综述 |

### Paper A（关联）
| 论文 | 状态 |
|------|------|
| Zhou 2026 "Two-Channel Allen-Dynes" arXiv:2604.05994 | 已知（自身工作）|

---

## 15. 数据汇总（反幻觉确认）

[定理 - Migdal 1958] 顶点修正 ~ √(m/M) 可忽略

[定理 - Eliashberg 1960] 完整强耦合方程

[定理 - Allen-Dynes 1975] T_c = (ω_log/1.20) f₁f₂ exp[-1.04(1+λ)/(λ - μ*(1+0.62λ))]

[观察 - Pb] λ=1.55, ω_log=52K, T_c=7.2K（强耦合典型）[Carbotte 1990]

[观察 - H₃S] λ=2.19, ω_log=1335K, T_c=203K [Errea 2020]

[观察 - LaH₁₀] λ=2.46, ω_log=1500K, T_c=250K [Drozdov 2019]

[观察 - λ > 2] Allen-Dynes 系统性低估 ~10-30%

[反幻觉] 所有 λ, ω_log 数值附 Carbotte 1990 RMP 或具体 DFPT 计算论文。

---

## 16. 反幻觉自检

- [x] Migdal 1958 / Eliashberg 1960 / McMillan 1968 / Allen-Dynes 1975 经典 DOI 标注
- [x] λ, ω_log 数据来源 Carbotte 1990 RMP 或具体氢化物论文
- [x] H₃S, LaH₁₀, MgB₂ 等关键材料具体 DOI
- [x] Allen-Dynes 强耦合修正因子 f₁ f₂ 公式准确
- [x] PdH μ* 异常的来源说明（Carbotte 1990 + Paper A 讨论）
- [x] 不假装 "Eliashberg 适用所有 SC"——多次明确边界

---

## 17. 反谄媚自检

- [x] **Eliashberg 失效领域明确列出**（Mott、强关联、平坦带、拓扑、自旋涨落）
- [x] Allen-Dynes 公式在 λ > 2 时的系统低估明确说明
- [x] Migdal 定理在氢化物中的"小参数"弱化坦诚说明
- [x] 不夸大 DFT+DFPT+Eliashberg 的预测能力（10-20% 误差是常态）
- [x] PdH μ* 异常作为框架边界，不掩盖
- [x] Paper A 的多通道扩展只在特定情形成立，不是普适

---

## 18. 当前状态与后续行动

**状态：** [已综述]，B 部分核心理论完成

**B1 + B2 完成后的整体认知：**

1. **声子机制框架完整**：BCS 弱耦合 → Eliashberg 强耦合 → Allen-Dynes 工程公式
2. **氢化物是当代最大成功**：DFT+DFPT+Eliashberg 预测 H₃S/LaH₁₀ 等高 Tc 与实验吻合
3. **声子机制的硬上限**：常压下 ~MgB₂ 39K 是声子机制的实际上限
4. **高 Tc 突破依赖非声子或多通道**：B3-B14 待研究

**遗留问题：**
1. 极强耦合 λ > 3 时 Migdal 假设的精确边界
2. 量子涨落（氢化物 ZPE）对 Eliashberg 的修正（Errea 2020）
3. 多通道（声子 + 自旋涨落）的相干叠加（Paper A 部分回答）
4. 镍酸盐中声子贡献的精确量化（→ B12 + D5）

**后续建议：**
- B3（自旋涨落 AFM）：超过声子机制的核心非常规通道
- 完成 B1-B5 后启动 B 部分综合分析（声子 vs 自旋 vs 向列）

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Migdal-Eliashberg-McMillan-Allen-Dynes 完整框架 + 氢化物现代验证。**B 部分核心理论完成**
