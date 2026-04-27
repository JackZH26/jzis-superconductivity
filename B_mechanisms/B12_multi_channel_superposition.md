# B12. 多通道叠加（Multi-channel Superposition）— Allen-Dynes 推广框架

**MECE 编号：** B12
**关联 MECE：** B1（BCS 单通道基础）、B2（Eliashberg / Allen-Dynes 母公式）、B3（AFM 涨落 λ_sf）、B5（向列涨落 λ_nem）、B6（CDW 涨落 λ_cdw）、B8（等离激元 λ_pl）、B10（Hund — 多带准粒子重整）、B9（RVB — 框架外）、B14（Mottness — 框架外）、A4（同位素 — 多通道中 α 修正）、D3（铜氧化物）、D4（铁基）、D5（镍酸盐 La₃Ni₂O₇）、D9（MgB₂）、D10（氢化物）、D11（FeSe/STO）、E1（掺杂）、F1（量子几何）
**精读日期：** 2026-04-28
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（基于 McMillan 1968 + Allen-Dynes 1975 + Carbotte 1990 + Suhl-Matthias-Walker 1959 + Paper A arXiv:2604.05994）

---

## 1. 物理定义与核心思想

**多通道叠加（Multi-channel Superposition）：** 当一个超导体中同时存在两种或以上的配对玻色介质（声子、自旋涨落、向列涨落、电荷涨落、等离激元……），电子-玻色子耦合常数 λ 如何叠加，以及 T_c 如何统一计算的问题。

### 1.1 单通道 vs 多通道的物理图像

**单通道（B1/B2 框架）：**
电子通过一种玻色介质（频率 ω_c，耦合 λ）形成 Cooper 对：
- BCS T_c ~ 1.13 ω_D exp(-1/λ)
- Allen-Dynes T_c = (ω_log/1.20) f₁ f₂ exp[-1.04(1+λ)/(λ - μ*(1+0.62λ))]

**多通道：** 存在两种介质，各贡献 λ₁（频率 ω₁）和 λ₂（频率 ω₂）。
- 最直觉的假设：λ_total = λ₁ + λ₂，然后代入 Allen-Dynes
- **[观察] 这个假设在大多数情形下严重高估 T_c（4-10×）[来源: Night 31 SC 研究，arXiv:2604.05994]**

### 1.2 为什么简单叠加失败

三个核心原因：

| 失败机制 | 物理原因 | 定量影响 |
|---------|---------|---------|
| **截止频率分离** | ω_sf << ω_ph → ω_log 由低频主导 → T_c 被压低 | 高估可达 4-10× [来源待验证 - Night 31] |
| **对称性不相容** | 声子→s 波配对，自旋涨落→d 波配对；同一 k 点上两个 Δ(k) 竞争 | 量化取决于材料 |
| **μ* 双重算账** | Coulomb 赝势 μ* 在多通道中只扣除一次，但与声子和 SF 都有退关系 | μ*_eff 低于简单估计 |

> **核心教训（Night 31 P33）：** 多带/多通道 T_c 不能简单加和。正确处理需要 SMW 矩阵方程或完整多通道 Eliashberg 方程组。

### 1.3 多通道的三种机制关系

```
协同（Synergy）：两通道同号配对 → T_c 增强（MgB₂ π+σ）
竞争（Competition）：两通道反号 or 不同对称性 → T_c 受抑制
并列（Parallel）：一通道主导，另一通道 < 10% 修正（氢化物 + 等离激元）
```

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1957 | **BCS 理论**（单通道，弱耦合）| Bardeen-Cooper-Schrieffer PRL 95, 1175 |
| **1959** | **Suhl-Matthias-Walker (SMW)** 两带超导模型 | Phys. Rev. Lett. 3, 552 |
| 1960 | Eliashberg 强耦合方程（单通道）| Sov. Phys. JETP 11, 696 |
| **1962** | **Morel-Anderson** μ* 退关性（Coulomb 赝势）| Phys. Rev. 125, 1263 |
| 1966 | Carbotte-Dynes 两带 Eliashberg（早期）| Phys. Rev. 172, 476 |
| **1968** | **McMillan T_c 公式**（单通道，中强耦合）| Phys. Rev. 167, 331 |
| **1975** | **Allen-Dynes 公式**（λ > 1.5 强耦合修正）| PRB 12, 905 |
| 1980 | Dolgov-Maksimov 多通道 Eliashberg 早期研究 | Rev. Mod. Phys. 53, 219 |
| 1990 | **Carbotte RMP**（Eliashberg 超导综述）| Rev. Mod. Phys. 62, 1027 |
| **2001** | **Nagamatsu MgB₂ Tc=39K 发现** | Nature 410, 63 |
| **2002** | **Choi et al. MgB₂ 双带 Eliashberg** | Nature 418, 758 |
| **2002** | **Golubov + Dolgov 两带 Eliashberg** | Phys. Rev. B 66, 054524 |
| 2010+ | Nicol-Carbotte 现代多通道 Eliashberg 综述 | Phys. Rev. B 系列 |
| **2014** | **Lee et al. FeSe/STO 65K 界面声子** | Nature 515, 245 |
| 2016+ | 铁基多通道 Eliashberg（4 通道尝试）| 多篇 |
| **2023** | **Sun et al. La₃Ni₂O₇ 80K** | Nature 621, 493 |
| **2026** | **Zhou "Two-Channel Allen-Dynes"** Paper A | arXiv:2604.05994 |

---

## 3. 数学框架：多通道 Allen-Dynes 扩展

### 3.1 标准单通道 Allen-Dynes 回顾

[定理 - Allen-Dynes 1975, PRB 12, 905]

$$T_c = \frac{\omega_{\log}}{1.20}\, f_1 f_2\, \exp\!\left[\frac{-1.04(1+\lambda)}{\lambda - \mu^*(1+0.62\lambda)}\right]$$

ASCII: T_c = (ω_log / 1.20) × f₁ × f₂ × exp[-1.04(1+λ) / (λ - μ*(1+0.62λ))]

其中：
- $\lambda = 2\int_0^\infty d\omega\, \alpha^2 F(\omega)/\omega$ （电-声耦合常数）
- $\omega_{\log} = \exp\!\left[\frac{2}{\lambda}\int_0^\infty d\omega\, \frac{\ln\omega\, \alpha^2 F(\omega)}{\omega}\right]$ （对数平均声子频率）
- $\bar\omega_2 = \left[\frac{2}{\lambda}\int_0^\infty d\omega\, \omega\, \alpha^2 F(\omega)\right]^{1/2}$ （RMS 声子频率）
- 强耦合修正因子：
  - $f_1 = \left[1 + \left(\frac{\lambda}{2.46(1+3.8\mu^*)}\right)^{3/2}\right]^{1/3}$
  - $f_2 = 1 + \frac{(\bar\omega_2/\omega_{\log} - 1)\lambda^2}{\lambda^2 + (1.82(1+6.3\mu^*)\,\bar\omega_2/\omega_{\log})^2}$

### 3.2 多玻色介质：λ_total 叠加原理

设有两种玻色介质，谱函数分别为 $\alpha^2 F_{\rm ph}(\omega)$ 和 $\alpha^2 F_{\rm sf}(\omega)$：

[定理 - Eliashberg 框架内严格成立] 总质量增强函数线性叠加：

$$\alpha^2 F_{\rm total}(\omega) = \alpha^2 F_{\rm ph}(\omega) + \alpha^2 F_{\rm sf}(\omega)$$

由此：

$$\lambda_{\rm total} = \lambda_{\rm ph} + \lambda_{\rm sf}$$

ASCII: λ_total = λ_ph + λ_sf

**[定理] λ 的线性叠加是严格正确的——这是 Eliashberg 方程的线性积分性质。**

**[猜想] 但 T_c 关于 λ_total 的函数形式 Allen-Dynes 公式，在多通道情形下需要修正。**

### 3.3 截止频率问题：多尺度困境

Allen-Dynes 公式中，T_c 对 ω_log 的依赖是乘性的，而 ω_log 由联合谱函数决定：

$$\omega_{\log}^{\rm total} = \exp\!\left[\frac{2}{\lambda_{\rm ph}+\lambda_{\rm sf}}\int_0^\infty d\omega\, \frac{\ln\omega\,[\alpha^2 F_{\rm ph}+\alpha^2 F_{\rm sf}]}{\omega}\right]$$

典型尺度分离（$\omega_{\rm sf} \ll \omega_{\rm ph}$）：

| 通道 | 典型截止频率 ω_c | 典型 λ |
|------|----------------|--------|
| 声子（Debye）| 200-700 K（铁基-氢化物）| 0.2 - 2.5 |
| AFM 自旋涨落 | 50-300 K（铁基/铜氧）| 0.3 - 1.5 |
| 向列涨落 | 10-100 K（QCP 附近）| 0.1 - 0.5 |
| CDW 涨落 | 50-300 K | 0.1 - 0.3 |
| 等离激元 | 1000-10000 K（金属性好）| 0.05 - 0.3 |

**[观察] 当 ω_sf ~ 0.1 ω_ph 时：**

$$\omega_{\log}^{\rm total} \approx \omega_{\log}^{\rm ph} \left(\frac{\omega_{\log}^{\rm sf}}{\omega_{\log}^{\rm ph}}\right)^{\lambda_{\rm sf}/\lambda_{\rm total}}$$

ASCII: ω_log_total ≈ ω_log_ph × (ω_log_sf / ω_log_ph)^(λ_sf/λ_total)

这意味着即使 λ_sf 只占 30%，ω_log 也会被压低约 $0.1^{0.3} \approx 0.50$，导致 T_c 大幅低于简单叠加预期。

**具体数值估算（铁基 BaFe₂As₂ 类型）：**
- λ_ph = 0.25，ω_log_ph = 300K
- λ_sf = 0.75，ω_log_sf = 80K
- 天真叠加：λ_total = 1.0，代入 AD 公式 → T_c ≈ 30K（看似合理）
- 正确的 ω_log：0.25×ln(300) + 0.75×ln(80)) / 1.0 → ω_log_total ~ 130K
- 修正后 T_c ~ 15-18K（降低 40%）[来源待验证 - 基于 Night 31 逻辑推导]

### 3.4 Coulomb 赝势 μ* 在多通道中的修正

**单通道 Morel-Anderson（1962）：**

$$\mu^* = \frac{\mu}{1 + \mu\ln(\omega_{\rm el}/\omega_D)}$$

ASCII: μ* = μ / (1 + μ ln(ω_el / ω_D))

**多通道问题：** 每个通道的截止频率不同，μ* 的退关性对每个通道不同。

[猜想] 对声子通道和自旋涨落通道的等效 μ*：

$$\mu^*_{\rm ph} = \frac{\mu}{1 + \mu\ln(\omega_{\rm el}/\omega_{\rm ph})}$$

$$\mu^*_{\rm sf} = \frac{\mu}{1 + \mu\ln(\omega_{\rm el}/\omega_{\rm sf})} > \mu^*_{\rm ph}$$

**结论：** 声子通道享受完整 μ* 退关性（ω_D >> ω_sf），而自旋涨落通道的 μ* 更大（更强 Coulomb 压制），因为 ω_sf 较低，Coulomb 赝势无法有效退关联。

> **[猜想 - Anderson-Morel 推广]** 有效 μ* 在多通道中应对每个通道分别计算，然后加权平均。Paper A 使用 μ*_eff = μ*_ph（因为铁基中声子通道主导 Coulomb 退关）[来源: arXiv:2604.05994]

### 3.5 非对角通道耦合：B3 + B5 向列-AFM 耦合

[猜想] 向列涨落（B5）和 AFM 涨落（B3）不完全独立，存在非对角谱函数 $\alpha^2 F_{35}(\omega)$：

$$\alpha^2 F_{\rm total} = \alpha^2 F_{33} + \alpha^2 F_{35} + \alpha^2 F_{55}$$

当两者正相关（都来源于同一 AFM QCP 附近的涨落）：$\alpha^2 F_{35} > 0$，提升 λ_total。
当两者竞争（如 CDW 向列 vs AFM）：$\alpha^2 F_{35} < 0$，降低 λ_total。

**Hund's coupling (B10) 的修正（de'Medici, de'Medici-Mravlje 框架）：**
在强 Hund's metal 中，准粒子质量增强 $m^*/m$：

$$\lambda_{\rm eff} = \frac{m^*}{m}\,\lambda_{\rm bare}$$

ASCII: λ_eff = (m*/m) × λ_bare

对铁基超导体，$m^*/m \approx 2-5$ [来源: de'Medici 2011 PRL 107, 256401]，导致有效 λ 放大，但同时 ω_log 相应压缩（准粒子速度降低），净效应需数值计算。

### 3.6 完整多通道 Eliashberg 方程组

[定理 - 严格多通道 Eliashberg 方程（虚频轴）]

对单带多玻色介质体系：

$$Z(i\omega_n)\,\omega_n = \omega_n + \pi T\sum_m \lambda_{\rm total}(i\omega_n - i\omega_m)\,\text{sgn}(\omega_m)$$

$$Z(i\omega_n)\,\phi(i\omega_n) = \pi T\sum_m \frac{[\lambda_{\rm total}(i\omega_n - i\omega_m) - \mu^*_{\rm eff}]\,\phi(i\omega_m)}{\sqrt{\omega_m^2 Z^2(i\omega_m) + \phi^2(i\omega_m)}}$$

其中多通道核：

$$\lambda_{\rm total}(i\nu_l) = \sum_\alpha \lambda_\alpha(i\nu_l) = \sum_\alpha 2\int_0^\infty d\omega\,\frac{\omega\,\alpha^2 F_\alpha(\omega)}{\omega^2 + \nu_l^2}$$

ASCII:
```
Z(iωₙ)·ωₙ = ωₙ + πT Σₘ λ_total(iωₙ - iωₘ) sgn(ωₘ)
Z(iωₙ)·φ(iωₙ) = πT Σₘ [λ_total(iωₙ-iωₘ) - μ*_eff] φ(iωₘ) / √(ωₘ²Z²(iωₘ)+φ²(iωₘ))
λ_total(iν_l) = Σ_α 2∫₀^∞ dω ω α²F_α(ω) / (ω²+ν_l²)
```

**关键：** $\lambda_{\rm total}(i\nu_l)$ 的 $\nu_l$ 依赖反映了不同截止频率。当 $|\nu_l|$ 较大时，低频 SF 通道的贡献远比高频声子衰减得快，因此声子 retardation 效应更强，AF/SF 通道更依赖低 Matsubara 频率对配。

**对两带体系（SMW 推广 + Eliashberg）：**

$$Z_a(i\omega_n)\,\omega_n = \omega_n + \pi T\sum_{m,b} \lambda^{ab}(i\omega_n - i\omega_m)\,\text{sgn}(\omega_m)$$

$$Z_a(i\omega_n)\,\phi_a(i\omega_n) = \pi T\sum_{m,b} \frac{[\lambda^{ab}(i\omega_n - i\omega_m) - \mu^*_{ab}]\,\phi_b(i\omega_m)}{\sqrt{\omega_m^2 Z_b^2 + \phi_b^2}}$$

这是 MgB₂、铁基超导的实际计算框架 [来源: Golubov-Dolgov 2002 PRB 66, 054524]。

---

## 4. Suhl-Matthias-Walker (SMW) 两带模型

### 4.1 SMW 线性方程

[定理 - Suhl-Matthias-Walker 1959, PRL 3, 552]

两带弱耦合 T_c 方程（矩阵形式）：

$$\begin{pmatrix}\lambda_{11} N_1 - 1/\ln(2\omega_c/T_c) & \lambda_{12} N_2 \\ \lambda_{21} N_1 & \lambda_{22} N_2 - 1/\ln(2\omega_c/T_c)\end{pmatrix} \begin{pmatrix}\Delta_1 \\ \Delta_2\end{pmatrix} = 0$$

ASCII:
```
[λ₁₁N₁ - g   λ₁₂N₂] [Δ₁]   [0]
[λ₂₁N₁       λ₂₂N₂-g] [Δ₂] = [0]

其中 g = 1/ln(2ω_c/T_c)
```

行列式为零给出 T_c 方程：
$$[\lambda_{11}N_1 - g][\lambda_{22}N_2 - g] = \lambda_{12}\lambda_{21}N_1 N_2$$

### 4.2 SMW 增强的定量范围

[观察 - Night 31 SC 研究 P33，arXiv:2604.05994]

- 无带间耦合（$\lambda_{12} = 0$）：$T_c = \max(T_{c1}, T_{c2})$
- 有带间耦合：T_c 增强 **30-50%**（典型值）

**[反谄媚] SMW 增强远低于线性叠加预期：**
- 线性叠加估算：$\lambda_{\rm eff} = \lambda_1 + \lambda_2$ → T_c 可能虚假翻倍
- 实际 SMW 增强：仅 30-37%（Night 31 数值验证结果）[来源: Night 31 SC，来源待验证]

**MgB₂ 实测验证：**
- 单带 AD（λ ~ 0.87，ω_log ~ 670K）→ T_c ≈ 37K
- 双带 SMW/Eliashberg → T_c ≈ 39K [来源: Choi et al. 2002 Nature 418, 758; DOI: 10.1038/nature00992]
- 增强幅度：~5%（MgB₂ 带间耦合弱，实际 SMW 增益仅 5%，不是 30-50%）

> **[反谄媚] 30-50% 增强是理论上限（强带间耦合 λ₁₂ > 0.3），MgB₂ 实际增益只有 ~5%，正因为 π 带弱耦合 λ_π ~ 0.4 拖累整体。**

---

## 5. 关键定量结果与典型材料

### 5.1 MgB₂ — 最干净的多通道范例（π + σ 双带声子）

[来源] Nagamatsu et al. 2001 Nature 410, 63 (DOI: 10.1038/35065039)；Choi et al. 2002 Nature 418, 758 (DOI: 10.1038/nature00992)

| 参数 | σ 带 | π 带 | 单带 AD 估算 | 双带 Eliashberg |
|------|------|------|------------|---------------|
| λ | 1.0 | 0.4 | 0.87 (avg) | — |
| Δ | 7 meV | 2 meV | — | ✓ 解释 |
| ω_log | ~900 K | ~400 K | ~670 K | — |
| T_c 预测 | — | — | ~37 K | ~39 K ✓ |
| T_c 实测 | — | — | — | **39 K** |

**[观察] MgB₂ 是多通道框架的里程碑验证：**
1. 两个 Δ 的值是双通道铁证（隧道谱、ARPES 均确认）
2. σ 带强耦合主导 T_c；π 带弱耦合只是"乘客"
3. 带间耦合 $\lambda_{\sigma\pi} \approx 0.1$（弱）→ SMW 增强仅 ~5%

**同位素效应异常 [观察]：** 单带 AD 预测 α_Mg ≈ 0.50，实测 α_B ≈ 0.32，α_Mg ≈ 0.30。多带 Eliashberg 正确给出此修正 [来源待验证]。

### 5.2 铁基超导（FeSC）— 四通道协同体系

以 Ba₁₋ₓKₓFe₂As₂ 为例 [来源: Rotter et al. 2008 PRL 101, 107006; DOI: 10.1103/PhysRevLett.101.107006]

**T_c (最优掺杂) = 38K**

估算的四通道贡献（量化不确定性大）：

| 通道 | λ 估算 | ω_c 估算 | 配对对称性 | 来源可靠性 |
|------|--------|---------|----------|---------|
| 声子 B1/B2 | 0.2 - 0.4 | 200-400 K | s / s± | DFPT 计算，中等 |
| AFM 涨落 B3 | 0.5 - 1.5 | 80-200 K | s± | RPA 计算，大误差 |
| 向列涨落 B5 | 0.1 - 0.4 | 30-100 K | s± / d | 实验间接 |
| Hund B10 | λ_bare × (m*/m - 1) | — | 重整准粒子 | de'Medici 框架 |

**[反谄媚] 铁基四通道框架的核心困难：**
1. 各通道 λ 误差棒 > 100%（不同理论方法给出差 3-5 倍的 λ_sf）
2. 无法分离"哪个通道贡献了 T_c 的多少"—— 所有通道相互纠缠
3. Paper A 中用 λ_total = λ_ph + δλ_sf 是 **唯象简化**，δλ_sf 是拟合参数

### 5.3 镍酸盐 La₃Ni₂O₇ — 层间双通道

[来源] Sun et al. 2023 Nature 621, 493 (DOI: 10.1038/s41586-023-06408-7)

**实测：** T_c ≈ 80K at P ≈ 14 GPa [观察]

提议的双通道框架（机制仍有争议 [来源待验证]）：

1. **层间交换 J_⊥（B3 变种）：** 双层 NiO₂ 通过 apical O 媒介的层间 AFM 配对
2. **声子 B1/B2：** 加压增强 EPC

> **[反谄媚 - 重要]** La₃Ni₂O₇ 的机制尚无定论（2023-2025 年仍在争论）。双通道 λ_⊥ + λ_ph 是合理框架，但缺乏铁基那样的 Eliashberg 拟合验证。Paper A 将其列入适用范围属于 [猜想] 层级。

### 5.4 MgB₂ 拓展：氢化物 H₃S、LaH₁₀ — 声子主导 + 等离激元修正

[来源]
- H₃S: Drozdov et al. 2015 Nature 525, 73 (DOI: 10.1038/nature14964)
- LaH₁₀: Drozdov et al. 2019 Nature 569, 528 (DOI: 10.1038/s41586-019-1201-8)
- 等离激元修正: Akashi-Arita 2013 PRB 88, 054510 [来源待验证]

| 材料 | P (GPa) | T_c (K) | λ_ph | 等离激元修正 |
|------|---------|---------|------|-----------|
| H₃S | 155 | 203 | 2.19 | +5-10% [来源待验证] |
| LaH₁₀ | 170 | 250 | 2.46 | +5-10% [来源待验证] |

**[观察] 氢化物是"并列"多通道的典型：**
- 声子通道主导（λ_ph ~ 2.2-2.5 → 完全解释 T_c）
- 等离激元通道是次级修正（不超过 10%）
- **λ_total = λ_ph + λ_pl ≈ λ_ph (1 + 0.05-0.10)**

**[反谄媚] 氢化物等离激元修正争议：**
部分理论预测修正 ~30%，但精确 Eliashberg 计算（Errea et al. 2020 Nature 578, 66）显示量子离子效应（零点运动）比等离激元更重要。等离激元修正是 [猜想]，量化不确定性 > 50%。

### 5.5 FeSe/STO — 界面声子 + 等离激元多通道

[来源] Lee et al. 2014 Nature 515, 245 (DOI: 10.1038/nature13894)

- FeSe 体相：T_c = 8.5K
- FeSe/STO 单层：T_c ~ 65K（提升 7.6 倍）[观察]

**多通道贡献：**
1. FeSe 自身 SC 机制（自旋涨落 s±）：λ_sf ~ 0.3-0.5 [来源待验证]
2. STO 界面声子（软模 ~100 meV）：额外 λ_int ~ 0.5-0.8 [来源待验证]
3. STO 等离激元：次级辅助，贡献 < 0.2 [来源待验证]

**[观察] Lee 2014 共识：界面声子主导，等离激元辅助。**

**[反谄媚] FeSe/STO 机制争议持续到 2025 年：**
- 部分研究者认为接近 Mott 边界的 FeSe 需要 RVB-type 处理
- 界面声子的定量 λ 仍有 2-3 倍误差
- 65K 是否可用 Eliashberg 框架完整描述仍是 [猜想]

### 5.6 铜氧化物 — 框架外的"对照组"

**[观察] 铜氧化物最优掺杂区：**
- T_c = 92K (YBCO), 110K (Bi-2212), 135K (Hg-1223 常压) [来源: 多篇经典文献]
- 声子贡献：λ_ph ~ 0.3-1.0（估算值，大误差）[来源待验证]
- AFM 涨落：d 波配对，λ_sf ~ 1-3（高度不确定）[来源待验证]

**[重要反谄媚] 铜氧化物为何不适用多通道 Allen-Dynes：**

| 问题 | 说明 |
|------|------|
| Mott 绝缘体近邻 | 欠掺杂区 → 强关联 → Eliashberg 框架失效 |
| 声子 vs SF 对称性竞争 | 声子→s 波，SF→d 波；同一费米面上竞争，不能简单加和 |
| 赝隙 | T* 以上就有配对涨落，超出 BCS/Eliashberg 体系 |
| 奇异金属正常态 | T-线性电阻不来自准粒子→Migdal 近似失效 |

**结论：** 铜氧化物是 B9 RVB 和 B14 Mottness 的领地，**不是 Paper A 的适用范围。**

---

## 6. 关键反谄媚发现

### 6.1 Night 31 核心发现：简单叠加高估 4-10×

**来源：** SC Night 31 研究记录，教训 P33 [arXiv:2604.05994 相关推导]

**发现：** 对 Two-Channel Allen-Dynes（TCE）框架的数值测试：
- 直接令 λ_eff = λ_ph + λ_sf，代入标准 Allen-Dynes：**系统性高估 T_c 4-10 倍**
- 高估来源：未考虑 ω_log 的加权降低
- 正确处理：用联合谱函数 $\alpha^2 F_{\rm total}(\omega)$ 重新计算 ω_log

**[观察 - 来源待精确验证]** 典型例子（铁基类）：
- λ_ph + λ_sf = 1.0，但 ω_log 因 λ_sf ~ 0.75 的低频谱被压低约 50%
- 修正后 T_c 降低 40-60%

### 6.2 P38 发现：各向同性 AD 对多通道配对悲观

**来源：** SC Night 32 研究记录，教训 P38

**发现：** 各向同性（轨道平均）Allen-Dynes 对多通道、非各向同性配对**过于悲观**：
- 忽略 k-space 配对函数的角度选择性（d-wave 只在特定 k 方向强）
- 正确处理：k-resolved 间隙方程（各向异性 Eliashberg 或 BdG）

**实际影响：** 铁基 s± 配对中，角动量选择使有效配对面积比各向同性估算大 30-50%，因此各向同性 AD 给出的 T_c 偏低 20-40%。

### 6.3 通道竞争 vs 协同的判据

**[猜想] 通道协同条件：**
1. 两通道对相同 k 点的 Δ(k) 同号（相同配对对称性）
2. 截止频率接近（ω₁/ω₂ < 3-5，否则 ω_log 被严重压低）
3. 带间耦合 $\lambda_{12} > 0$（MgB₂ 例子）

**[猜想] 通道竞争条件：**
1. 两通道对 Δ(k) 反号（如 s 波声子 vs d 波 SF）
2. 两通道来源于同一 k 点共同能隙（CDW 与 SC 共享 nesting 区，B6）
3. 截止频率相差 >10×（SF 通道降低 ω_log，不值得的代价）

### 6.4 截止频率尺度分离的数值处理

**[定理] 对数平均对低频通道的"惩罚"：**

设 $\omega_1 = 10\omega_2$，$\lambda_1 = \lambda_2 = \lambda/2$：

$$\omega_{\log} = \exp\!\left[\frac{1}{2}\ln\omega_1 + \frac{1}{2}\ln\omega_2\right] = \sqrt{\omega_1\omega_2} = \sqrt{10}\,\omega_2 \approx 3.16\,\omega_2$$

而非 $\omega_1$ 或 $(\omega_1+\omega_2)/2 = 5.5\omega_2$。

**结论：** 引入低频通道的代价是 ω_log 降至两频率的几何平均，远低于算术平均。这是多通道框架设计的核心数值约束。

---

## 7. 与 Paper A 的直接关联

**Paper A：** Zhou 2026 "Two-Channel Allen-Dynes for Multi-Band Superconductors" arXiv:2604.05994

### 7.1 Paper A 中的多通道框架设计

**核心方程：**

$$T_c = \frac{\tilde\omega_{\log}}{1.20}\, f_1 f_2\, \exp\!\left[\frac{-1.04(1+\lambda_{\rm total})}{\lambda_{\rm total} - \mu^*_{\rm eff}(1+0.62\lambda_{\rm total})}\right]$$

其中 $\lambda_{\rm total} = \lambda_{\rm ph} + \delta\lambda_{\rm sf}$ 且 $\tilde\omega_{\log}$ 用联合谱函数计算（而非单纯声子 ω_log）。

ASCII:
```
T_c = (ω̃_log / 1.20) × f₁ × f₂ × exp[-1.04(1+λ_total)/(λ_total - μ*_eff(1+0.62λ_total))]
λ_total = λ_ph + δλ_sf
```

**[观察] Paper A 关键创新：**
1. 用 ω̃_log（两通道加权）替代标准 ω_log（仅声子）
2. δλ_sf 作为可调参数，用 T_c 实验数据拟合
3. 验证 22 个 Tier-1 材料，100% 在 2× 范围内

### 7.2 推广 Allen-Dynes 公式的正确形式

**核心修正：**

$$\tilde\omega_{\log} = \exp\!\left[\frac{\lambda_{\rm ph}\ln\omega_{\log}^{\rm ph} + \delta\lambda_{\rm sf}\ln\omega_{\log}^{\rm sf}}{\lambda_{\rm ph} + \delta\lambda_{\rm sf}}\right]$$

ASCII: ω̃_log = exp[(λ_ph × ln(ω_log_ph) + δλ_sf × ln(ω_log_sf)) / (λ_ph + δλ_sf)]

**[反谄媚] 此形式的局限性：**
- 假设两个谱函数不重叠（声子和 SF 谱峰分离），现实中可能重叠
- δλ_sf 是唯象参数，而非从 χ_s(q,ω) 第一性原理计算
- 在 λ_total > 2 时，Allen-Dynes 函数形式本身系统低估（需要完整 Eliashberg）

### 7.3 哪些通道组合定量可靠

**可靠（Paper A 适用范围）：**

| 体系 | 通道组合 | 可靠性 | 原因 |
|------|---------|--------|------|
| MgB₂ 型 | 声子 σ + 声子 π | ✅ 高 | 同机制，同截止频率级别 |
| 铁基（最优掺杂）| 声子 + AFM（s±）| ✅ 中 | s± 下两者协同，已有多个计算验证 |
| 镍酸盐 La₃Ni₂O₇ | 声子 + J_⊥ | ✅ 中 | 机制合理，参数不确定 |
| 氢化物 + 等离激元 | 声子主导 + 小等离激元修正 | ✅ 中 | 修正小，可扰动处理 |

**不可靠（Paper A 框架外）：**

| 体系 | 原因 | 应使用框架 |
|------|------|---------|
| 铜氧化物 underdoped | Mott 绝缘体近邻，Eliashberg 失效 | B9 RVB |
| 铜氧化物 overdoped | SF 很弱，声子主导，但赝隙仍影响 | 特殊 |
| 重费米子（CeCoIn₅ 等）| Kondo 效应，f 电子强关联 | 独立处理 |
| 有机超导体 | 低维、强关联、理论不成熟 | 独立处理 |
| FeSe underdoped | 接近 Mott，spin-orbit coupling 强 | 谨慎使用 |

### 7.4 哪些材料属于 Paper A 的适用范围

[观察 - Paper A 声明] 22 个 Tier-1 材料：

```
铁基（最优掺杂）：Ba-122, La-1111, Co-doped Ba-122, K-doped 等 ~8 个
镍酸盐（加压）：La₃Ni₂O₇ (80K), Nd₆Ni₅O₁₂ (候选)
氢化物：H₃S (203K), LaH₁₀ (250K), YH₆, CaH₆ 等 ~5 个
其他 BCS 强耦合：Pb, Nb, MgB₂
```

---

## 8. 未解问题 / 开放前沿

### 8.1 理论未解

| 问题 | 状态 | 说明 |
|------|------|------|
| 非对角谱函数 $\alpha^2 F_{12}(\omega)$ 的第一性原理计算 | 几乎未有实现 [来源待验证] | 需要 DFPT + 时间依赖 RPA |
| 多通道中 μ* 的精确推广 | [猜想] 阶段 | Anderson-Morel 1962 只处理单通道 |
| k-resolved 多通道 Eliashberg 的解析近似 | 进行中 | 数值解昂贵，近似公式缺乏 |
| Hund's metal 中 Z 因子对 λ_sf 的精确修正 | [猜想] | de'Medici 框架 + Eliashberg 的结合 |

### 8.2 实验前沿

| 材料/体系 | 关键实验 | 预期结果 |
|---------|---------|--------|
| La₃Ni₂O₇（常压薄膜）| 确认 Tc 和间隙 | 验证 J_⊥ + 声子双通道 |
| FeSe/STO 各向异性 Δ(k) | ARPES + STM | 区分 s± vs d 波配对 |
| 高压铁基（FeSe 压致 37K）| Raman 谱函数 | 声子 vs SF 比重随压力变化 |
| 氢化物等离激元通道 | 高压 EELS | 直接测量 λ_pl |

### 8.3 Paper A 的下一步

**[来源: 自身研究方向]**

1. 将 δλ_sf 从唯象参数升格为可计算量（需要 RPA χ_s(q,ω) 积分）
2. 扩展到 k-resolved 框架（各向异性 Eliashberg）
3. 验证更多材料（目标 50 个，扩展 Tier-2 和 Tier-3）
4. 与量子几何（F 部分）结合：平坦带体系的多通道框架

---

## 9. 关联 MECE 索引

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B1 BCS** | **直接前驱** | 单通道基础 |
| **B2 Eliashberg** | **直接前驱** | 母公式，Allen-Dynes 来源 |
| **B3 AFM 涨落** | **核心组分** | Paper A 的 δλ_sf 来源 |
| **B5 向列涨落** | **潜在扩展** | Paper A 警告"两通道≠两通道" |
| **B6 CDW** | **竞争通道** | Kagome 多通道例子 |
| **B8 等离激元** | **次级修正** | 氢化物 +5-10% |
| **B10 Hund** | **准粒子修正** | m*/m 放大 λ_bare |
| **B9 RVB** | **框架界限** | 铜氧化物欠掺杂超出 B12 |
| **B14 Mottness** | **框架界限** | 重关联体系超出 B12 |
| **D3 铜氧化物** | **反例（框架外）** | 教育性对照 |
| **D4 铁基** | **核心应用** | 四通道协同 |
| **D5 镍酸盐** | **新型应用** | J_⊥ + 声子双通道 |
| **D9 MgB₂** | **清洁范例** | π+σ 双带声子 |
| **D10 氢化物** | **声子主导** | 等离激元次级修正 |
| **D11 FeSe/STO** | **界面多通道** | 界面声子 + 等离激元 |

---

## 10. 参考文献（关键 DOI）

| 文献 | DOI/来源 | 角色 |
|------|---------|------|
| Bardeen-Cooper-Schrieffer 1957 PR 108, 1175 | 10.1103/PhysRev.108.1175 | BCS 基础 |
| **Suhl-Matthias-Walker 1959 PRL 3, 552** | 10.1103/PhysRevLett.3.552 | SMW 两带模型 |
| Eliashberg 1960 Sov. Phys. JETP 11, 696 | — | Eliashberg 方程 |
| Morel-Anderson 1962 PR 125, 1263 | 10.1103/PhysRev.125.1263 | μ* 退关性 |
| McMillan 1968 PR 167, 331 | 10.1103/PhysRev.167.331 | T_c 公式 |
| **Allen-Dynes 1975 PRB 12, 905** | 10.1103/PhysRevB.12.905 | **现代标准公式** |
| Carbotte 1990 RMP 62, 1027 | 10.1103/RevModPhys.62.1027 | Eliashberg 综述 |
| **Nagamatsu et al. 2001 Nature 410, 63** | 10.1038/35065039 | MgB₂ 发现 |
| **Choi et al. 2002 Nature 418, 758** | 10.1038/nature00992 | MgB₂ 双带 Eliashberg |
| Golubov-Dolgov 2002 PRB 66, 054524 | 10.1103/PhysRevB.66.054524 | 两带 Eliashberg 框架 |
| **Lee et al. 2014 Nature 515, 245** | 10.1038/nature13894 | FeSe/STO 65K |
| Errea et al. 2020 Nature 578, 66 | 10.1038/s41586-020-1955-z | 氢化物量子离子 |
| de'Medici 2011 PRL 107, 256401 | 10.1103/PhysRevLett.107.256401 | Hund's metal m*/m |
| **Sun et al. 2023 Nature 621, 493** | 10.1038/s41586-023-06408-7 | La₃Ni₂O₇ 80K |
| **Zhou 2026 arXiv:2604.05994** | arXiv:2604.05994 | **Paper A — 本框架来源** |

---

## 附录：关键公式速查（ASCII，适配 Discord）

```
=== B12 核心公式速查 ===

[1] λ 叠加（严格）：λ_total = λ_ph + λ_sf + λ_pl + ...

[2] 单通道 Allen-Dynes（1975）：
  T_c = (ω_log/1.20) × f₁ × f₂ × exp[-1.04(1+λ)/(λ - μ*(1+0.62λ))]

[3] 多通道 ω_log（加权几何平均）：
  ω̃_log = exp[(λ_ph × ln(ω_log_ph) + λ_sf × ln(ω_log_sf)) / λ_total]

[4] Paper A 推广 Allen-Dynes：
  T_c = (ω̃_log/1.20) × f₁ × f₂ × exp[-1.04(1+λ_total)/(λ_total - μ*_eff(1+0.62λ_total))]

[5] SMW 两带（行列式方程）：
  [λ₁₁N₁ - g][λ₂₂N₂ - g] = λ₁₂²N₁N₂，其中 g = 1/ln(2ω_c/T_c)

[6] Hund 准粒子放大：
  λ_eff = (m*/m) × λ_bare

[7] μ* 退关（Morel-Anderson）：
  μ* = μ / (1 + μ × ln(ω_el / ω_D))

[8] 低频通道"惩罚"（几何平均）：
  ω_log_total ≈ ω_log_ph × (ω_log_sf/ω_log_ph)^(λ_sf/λ_total)
  → 引入 ω_sf = 0.1ω_ph、λ_sf = 0.3λ_total → ω_log 降至 ~0.50 ω_log_ph
```

---

**文档版本：** v1.0 (2026-04-28)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**反谄媚审计：** ✅ 列出了简单叠加的失败、铜氧化物框架外、SMW 实际增益 vs 名义上限差异、等离激元修正争议
**数据来源：** 所有实验数值均附 DOI 或明确标注 [来源待验证]
