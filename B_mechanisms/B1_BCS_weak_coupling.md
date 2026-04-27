# B1. BCS 弱耦合理论（Phonon-Mediated, Weak Coupling）

**MECE 编号：** B1
**关联 MECE：** B2（Eliashberg 强耦合扩展）、A3（比热 1.43）、A4（同位素 α=0.5）、A5（能隙 3.528）、C1（s 波）、D1（元素金属）、J1（理论方法）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 BCS 1957 + Cooper 1956 + Tinkham 1996 教科书）

---

## 1. 物理定义与核心思想

**BCS 理论：** 1957 年 Bardeen-Cooper-Schrieffer 提出的微观超导理论。核心论点：

> **金属中即使弱的电子-电子吸引相互作用（通过声子交换）也会让费米面上的电子在 (k↑, -k↓) 通道形成束缚 Cooper 对，凝聚为宏观相干波函数。**

**三个关键步骤：**
1. **Cooper 不稳定性**（Cooper 1956）：弱吸引 + 费米面 → 束缚态形成
2. **BCS 变分基态**：相干叠加多 Cooper 对
3. **平均场配对自洽**：能隙方程

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1933 | Meissner-Ochsenfeld 完全抗磁性发现 | Naturwissenschaften 21, 787 |
| 1935 | London 唯象方程 | Proc. Roy. Soc. A 149, 71 |
| 1950 | Ginzburg-Landau 理论 | ZhETF 20, 1064 |
| 1950 | **同位素效应**（Maxwell, Reynolds）→ 声子机制提示 | PRB 78, 477; 487 |
| 1956 | Fröhlich 电声子哈密顿量 | Phys. Rev. 79, 845 (1950 已有，1956 综述) |
| **1956** | **Cooper 不稳定性**：弱吸引下费米面束缚态 | Phys. Rev. 104, 1189 |
| **1957** | **BCS 完整理论**：变分基态 + 能隙 + 普适比 | Phys. Rev. 108, 1175 |
| 1958 | Bogoliubov 严格变换法 | Sov. Phys. JETP 7, 41 |
| 1959 | Mühlschlegel 精确数值表 | Z. Phys. 155, 313 |
| 1972 | Bardeen-Cooper-Schrieffer 共获诺贝尔物理学奖 | — |

---

## 3. Cooper 不稳定性（关键启动点）

### 3.1 Cooper 1956 的简单模型

考虑两个电子在已填满费米海上方，通过弱吸引势 V₀ < 0 相互作用。Cooper 证明：

[定理 - Cooper 1956] 对**任意小**的吸引（无论多小），(k↑, -k↓) 通道存在束缚态：
$$E_{\text{bound}} = -2\hbar\omega_D \exp\left(-\frac{2}{N(0) V_0}\right)$$

其中 N(0) 是 E_F 处态密度，ω_D 是 Debye 频率。

[来源] Cooper 1956 Phys. Rev. 104, 1189 [DOI: 10.1103/PhysRev.104.1189]

### 3.2 物理意义

**关键洞察：** 费米海的存在使弱吸引也能产生束缚态。这与三维空间中两电子在真空中**至少需要某临界吸引**才能束缚截然不同。

[关键] Pauli 不相容原理排斥的"剩余电子"被限制在 E > E_F 的薄壳中，等效降维 → 弱吸引足以束缚。

### 3.3 Cooper 不稳定性 → 多电子凝聚

Cooper 单对解必然不稳定 — 一旦一对形成，其他对也想形成。**自洽多体处理是必需**。这就引出 BCS 变分基态。

---

## 4. BCS 变分基态

### 4.1 变分波函数

[定义 - BCS 1957]
$$|\psi_{\text{BCS}}\rangle = \prod_{\mathbf{k}} \left( u_{\mathbf{k}} + v_{\mathbf{k}}\, \hat{c}^{\dagger}_{\mathbf{k}\uparrow} \hat{c}^{\dagger}_{-\mathbf{k}\downarrow}\right) |0\rangle$$

约束：|u_k|² + |v_k|² = 1

物理：
- |v_k|² 是 (k↑, -k↓) 对被占据的概率
- |u_k|² 是空着的概率
- 在 E_F 附近 u → v ≈ 1/√2 → 相干叠加

### 4.2 BCS Hamiltonian（约化）

[定义]
$$H_{\text{BCS}} = \sum_{\mathbf{k}\sigma} \xi_{\mathbf{k}} \hat{c}^{\dagger}_{\mathbf{k}\sigma} \hat{c}_{\mathbf{k}\sigma} + \sum_{\mathbf{k}, \mathbf{k}'} V_{\mathbf{k}\mathbf{k}'}\, \hat{c}^{\dagger}_{\mathbf{k}\uparrow} \hat{c}^{\dagger}_{-\mathbf{k}\downarrow} \hat{c}_{-\mathbf{k}'\downarrow} \hat{c}_{\mathbf{k}'\uparrow}$$

ξ_k = ε_k - E_F 是相对费米能的色散。

V_{kk'} 是有效配对相互作用（"BCS 模型"假设各向同性 + 局域）。

### 4.3 平均场近似

[定义 - 配对序参量]
$$\Delta_{\mathbf{k}} = -\sum_{\mathbf{k}'} V_{\mathbf{k}\mathbf{k}'}\, \langle \hat{c}_{-\mathbf{k}'\downarrow} \hat{c}_{\mathbf{k}'\uparrow}\rangle$$

在 BCS 模型（V_{kk'} = -V₀，常数）：
$$\Delta_{\mathbf{k}} = \Delta_0 \quad (\text{各向同性})$$

### 4.4 准粒子能谱

Bogoliubov 变换给出激发能：
$$E_{\mathbf{k}} = \sqrt{\xi_{\mathbf{k}}^2 + |\Delta_{\mathbf{k}}|^2}$$

最小激发能为 |Δ₀| → **能隙**。

---

## 5. BCS 自洽能隙方程

### 5.1 零温

[定理 - BCS 1957]
$$\frac{1}{N(0) V_0} = \int_0^{\hbar\omega_D} \frac{d\xi}{\sqrt{\xi^2 + \Delta_0^2}}$$

弱耦合极限 N(0) V₀ << 1：
$$\Delta_0 \approx 2\hbar\omega_D \exp\left(-\frac{1}{N(0) V_0}\right)$$

### 5.2 临界温度

[定理 - BCS 1957]
$$k_B T_c = \frac{2 e^{\gamma_E}}{\pi}\hbar\omega_D \exp\left(-\frac{1}{N(0) V_0}\right) \approx 1.134\,\hbar\omega_D \exp\left(-\frac{1}{N(0) V_0}\right)$$

其中 γ_E ≈ 0.5772 是 Euler-Mascheroni 常数。

### 5.3 BCS 三大普适比

[定理 - BCS + Mühlschlegel 1959]

| 比值 | 公式 | 数值 |
|------|------|------|
| **2Δ₀ / k_BT_c** | 2π e^(-γ_E) | **3.528** |
| **ΔC / γT_c** | 12 / [7ζ(3)] | **1.43** |
| **同位素 α** | 1/2（声子 ω_D ∝ M^(-1/2)）| **0.5** |

[来源] BCS 1957 PRB 108, 1175 [DOI: 10.1103/PhysRev.108.1175]

[来源] Mühlschlegel 1959 Z. Phys. 155, 313

---

## 6. BCS 假设的精确边界

[关键] BCS 严格成立要求**所有以下假设**满足：

| 假设 | 含义 | 失效体系 |
|------|------|---------|
| **弱耦合** N(0)V << 1 | 微扰论可用 | Pb, H₃S（强耦合）|
| **各向同性 V** | 球形 FS + s 波 | 铜氧化物（d 波）|
| **单一玻色频率** ω_D | 无频率结构 | MgB₂（双能隙）|
| **库仑屏蔽充分** μ* 小 | 不影响净吸引 | 氢化物（μ* > 0.1）|
| **远离磁性** | 无磁背景 | 重费米子、镍酸盐 |
| **远离 Mott** | U/W << 1 | 铜氧化物、镍酸盐 |
| **3D 大费米面** | 没有平坦带 | MATBG |
| **时间反演** | spin-singlet | UTe₂、Eu-nickelate（spin-triplet 候选）|

[反幻觉] BCS 在**元素金属**（Al, Sn, In）和**一些工业合金**（Nb-Ti）中严格成立。在**几乎所有 Tc > 30 K 的 SC 中**都至少部分失效。

---

## 7. BCS 严格成立的家族

### 7.1 元素金属（最佳验证）

| 材料 | T_c (K) | 2Δ/kBTc | ΔC/γTc | α | 来源 |
|------|---------|---------|--------|---|------|
| Al | 1.18 | 3.5 | 1.45 | 0.50 | Carbotte 1990 |
| Sn | 3.72 | 3.5 | 1.6 | 0.47 | 同上 |
| In | 3.41 | 3.6 | 1.7 | 0.49 | 同上 |
| Tl | 2.39 | 3.6 | 1.5 | 0.50 | 同上 |
| Ta | 4.47 | 3.6 | 1.6 | — | 同上 |

[观察] 这些材料的三个普适比都接近 BCS 预测，验证了 BCS。

### 7.2 偏离的元素

| 材料 | 2Δ/kBTc | ΔC/γTc | α | 偏离原因 |
|------|---------|--------|---|---------|
| Pb | 4.3 | 2.7 | 0.48 | 强耦合 |
| Hg | 4.6 | 2.4 | 0.50 | 强耦合 |
| Nb | 3.8 | 1.93 | — | 中等耦合 |
| Ru | — | — | **0.0** | 非声子主导? |

[观察] 当 λ ~ 1 时，BCS 普适比开始破坏。Eliashberg（B2）必要。

### 7.3 工业合金（应用相关）
| 材料 | T_c | BCS 适用？ | 备注 |
|------|-----|----------|------|
| Nb-Ti | 9.2 K | ✅ 大致 | MRI 应用 |
| Nb₃Sn | 18.3 K | △ 中等耦合 | 需 Eliashberg |
| Nb₃Ge | 23.2 K | △ 中等耦合 | 同上 |

---

## 8. BCS 框架不适用的体系

[反谄媚] 必须明确说出：BCS 在以下体系**不严格成立**或**完全失效**：

### 8.1 弱违反（修正 BCS 即可）
- Pb, Hg（强耦合，需 Eliashberg B2）
- MgB₂（双能隙，需双带 BCS）
- A15 化合物（强耦合）

### 8.2 中度违反（需要新框架）
- 高温铜氧化物（d 波 + 强关联）
- 铁基 SC（多带 + 自旋涨落）
- 镍酸盐（多带 + 强关联）

### 8.3 完全失效（BCS 概念不适用）
- **平坦带 SC**（MATBG）：N(0) → ∞，BCS Tc 公式发散
- **强关联 Mott 物理**（铜氧化物 underdoped）
- **Bose-Einstein 凝聚极限**（极强吸引）
- **拓扑 SC**（边界态主导）
- **spin-triplet SC**（UTe₂?, Eu-nickelate?）

---

## 9. BCS 的数学美

### 9.1 解析可解（极其难得）
BCS 是少数几个**解析可解**的多体问题：
- Cooper 不稳定性：单 pair 问题
- BCS 变分：变分参数显式求解
- 普适比：闭式解

### 9.2 普适比的物理含义
[未检验巧合] 2Δ₀/k_BT_c = 2π e^(-γ_E) ≈ 3.528 与 π + 1/φ² ≈ 3.524 偏差 0.114%（QSH-E7 中讨论）

### 9.3 与超流的对应
BCS Cooper pair 凝聚 ↔ ⁴He 玻色子凝聚（BEC-BCS crossover）
- BCS：极弱吸引，配对尺度 >> 粒子间距
- BEC：极强吸引，配对尺度 << 粒子间距
- 中间区：crossover

[来源] Eagles 1969, Leggett 1980, NSR 1985（理论框架），Regal-Greiner 2004（冷原子实验验证）

---

## 10. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B2 Eliashberg** | **直接扩展** | 强耦合修正 BCS |
| A3 比热 | **必然推论** | 1.43 来自 BCS |
| A4 同位素 | **判据** | 0.5 来自 BCS |
| A5 能隙 | **判据** | 3.528 来自 BCS |
| C1 s 波 | **核心** | BCS 默认 s 波 |
| D1 元素金属 | **测试场** | BCS 严格成立 |
| J1 理论方法 | 工具 | Bogoliubov 变换、自洽场 |
| F1 量子度规 | 不直接 | BCS 不含几何效应（平坦带例外）|

---

## 11. 推荐精读论文

### 必读（BCS 三部曲）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Cooper 1956** | DOI: 10.1103/PhysRev.104.1189 | 不稳定性（必读起点）|
| **Bardeen-Cooper-Schrieffer 1957** | DOI: 10.1103/PhysRev.108.1175 | **核心论文** |
| **Mühlschlegel 1959** | Z. Phys. 155, 313 | 精确数值 |

### 经典扩展
| 论文 | 来源 | 状态 |
|------|------|------|
| Bogoliubov 1958 | Sov. Phys. JETP 7, 41 | 严格变换法 |
| Anderson 1958 PR 110, 827 | DOI: 10.1103/PhysRev.110.827 | RPA 证明 BCS gauge invariance |
| Anderson 1959 J. Phys. Chem. Solids 11, 26 | Anderson's theorem | 弱杂质不破 s 波 SC |
| Carbotte 1990 RMP 62, 1027 | 强耦合数据集 | 必读 |

### 教科书
| 教科书 | 备注 |
|--------|------|
| Tinkham 1996, Ch.3 | McGraw-Hill, 必读基础 |
| Schrieffer 1999 "Theory of Superconductivity" | Westview Press |
| de Gennes 1966 | 经典 |
| Anderson 1984 "Basic Notions of Condensed Matter" | 哲学层面深 |

### 实验验证综述
| 论文 | 来源 | 状态 |
|------|------|------|
| Allen 1971 Solid State Physics 26, 53 | 同位素效应数据集 | 待精读 |
| Carbotte 1990 RMP | 强耦合修正 | 已提及 |

---

## 12. BCS 概念演化（21 世纪视角）

### 12.1 BCS 不是 SC 唯一理论

历史共识修正：
- 1957-1986：BCS 被认为是"普适"超导理论
- 1986+：高 Tc 铜氧化物发现彻底改变这个认识
- 现代：**BCS 只是一族 SC 理论中的一个 limit**

### 12.2 BCS 的"核心思想"仍然普适

虽然具体公式 Tc ∝ exp(-1/N V) 不普适，但以下 BCS 思想在所有 SC 理论中保留：
1. 配对（Cooper pair）作为基本激发
2. 变分基态 |ψ⟩ ~ Π(u + v c†c†)
3. 平均场序参量 Δ
4. 准粒子激发 E = √(ξ² + |Δ|²)

[关键] BCS 的"代数结构"（Bogoliubov 变换、序参量）在 spin-fluctuation、RVB、quantum metric 等所有现代理论中**保留**。BCS 失败的是**机制层面**（弱声子吸引），不是数学结构。

### 12.3 与膜框架（Paper E）的关系
[反谄媚] Paper E 已撤回过度声明：膜图像是 BCS 数学结构的几何重述，**不是新机制**。膜图像在 BCS 严格成立的体系中也成立 — 它是同一物理的不同语言。

---

## 13. 数据汇总（反幻觉确认）

[定理 - BCS 1957] T_c = (2 e^γ_E / π) ω_D exp(-1/NV) ≈ 1.134 ω_D exp(-1/NV)

[定理] 2Δ₀ / k_BT_c = 2π e^(-γ_E) ≈ 3.528

[定理] ΔC / γT_c = 12 / (7 ζ(3)) ≈ 1.43

[定理] 同位素效应 α = 1/2（声子主导）

[定理 - Cooper 1956] 任意小 V > 0 + 费米面 → 束缚态形成

[观察] 元素金属（Al, Sn, In, Tl）三个普适比都接近 BCS 预测

[观察] Pb, Hg 偏离明显（强耦合，需 Eliashberg）

[观察] 铜氧化物、铁基、镍酸盐 BCS 框架不适用（多个假设违反）

---

## 14. 反幻觉自检

- [x] Cooper 1956 + BCS 1957 + Bogoliubov 1958 等经典 DOI 标注
- [x] BCS 普适比的精确公式（不只数值）：2π e^(-γ_E), 12/(7ζ(3)), 1/2
- [x] Mühlschlegel 1959 数值表的来源
- [x] **BCS 假设清单完整**，不掩盖弱点
- [x] 元素金属数据（Al, Sn 等）来源 Carbotte 1990
- [x] 不假装"BCS 适用所有 SC"——多次明确说明边界
- [x] BEC-BCS crossover 来源 Eagles/Leggett/NSR/Regal-Greiner

---

## 15. 反谄媚自检

- [x] BCS 范式有限性多次明确（弱耦合 + s 波 + 各向同性 + 弱关联 + ...）
- [x] 失败的体系完整列出（包括 Pb 强耦合）
- [x] 现代 BCS 只是 SC 一族中的一个 limit
- [x] **Paper E 膜图像是 BCS 重述，不是新机制** — 直接说明
- [x] BEC-BCS crossover 的限制说明
- [x] 不夸大 Cooper 不稳定性"普适性"——它是费米液体 + 弱吸引的特殊结果

---

## 16. 当前状态与后续行动

**状态：** [已综述] — B 部分起点完成

**遗留问题：**
1. BCS 的精确数学结构如何在 spin-fluctuation / RVB / quantum metric 中保留？（→ B3, B9, F1）
2. BCS 在镍酸盐部分体系是否仍部分适用？（→ D5, B12 多通道）
3. UTe₂ 等 spin-triplet 候选的"BCS-like" 框架（→ G7, C9）
4. 与 Paper E 膜图像的精确对应（已在 Paper E 中讨论）

**后续：** B2（Eliashberg 强耦合）— BCS 的直接扩展，处理 Pb/H₃S 等强耦合体系

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。三大普适比 + 假设清单 + 与现代框架的关系。**B 部分起点**。
