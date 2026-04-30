# 精读笔记：Planckian Scattering and Parallel Conduction Channels in FeTe₁₋ₓSeₓ

**作者：** Ralph Romero III, Hee Taek Yi, Seongshik Oh, N. P. Armitage
**期刊：** Nature Physics 2026
**DOI：** 10.1038/s41567-026-03266-8
**arXiv：** 2505.00623 (2025-05-01 提交)
**精读日期：** 2026-04-25

---

## 1. 样品参数

| 样品 | x（Se/Te 比）| Tc | 备注 |
|------|------------|-----|------|
| Sample 1 | **x = 0.45** | **13.2 K** | 最佳掺杂，拓扑超导候选（Majorana 零模）|
| Sample 2 | **x = 0.35** | **11.8 K** | 更 overdoped |

- 100 nm 厚 FTS 薄膜（MBE）on 0.5 mm CaF₂(100) 基底
- 100 nm Se 封盖保护

---

## 2. 测量方法（TDTS）

- **Toptica TeraFlash Pro** 家制太赫兹时域光谱仪
- **频率范围：0.2 – 3 THz**
- **温度范围：1.4 K – 290 K**（液氦开流恒温器）
- 直接测量透射 E 场复数（幅度 + 相位）→ 直接得 σ₁(ν) 和 σ₂(ν)，无需 Kramers-Kronig
- 另有 DC 电阻作约束

---

## 3. 双通道分解

**模型：**
```
σ̃(ν) = S/(Γ − iν) + σ₀ + (π/2) S_δ δ(ν=0) + i S_δ/ν − iε₀(ε∞ − 1)ν
```
ε∞ = 4 固定（Homes et al. 2011）

### 宽通道（σ₀，"fast"）
- 频率无依赖的 Drude offset，Γ_fast >> 3 THz
- **温度依赖极弱**，**不参与超导凝聚**
- 代表**非相干背景**

### 窄通道（S/(Γ − iν)，"slow"）
- Γ 在 THz 窗口内可测量
- **Γ = Γ₀ + α · k_BT/ℏ**（线性 T 散射率 → Planckian）
- Spectral weight S 在 Tc 以下显著下降 → **这个通道进入凝聚体**

---

## 4. Planckian 边界（关键数字）

线性拟合 Γ(T) 在 20–40 K 范围：

| 样品 | **α（Planckian 乘数）** | Γ₀ |
|------|----------------------|-----|
| x = 0.45 | **α = 3.02** | ≈ 10 GHz |
| x = 0.35 | **α = 2.42** | < 10 GHz |

**两个样品均 α ≈ 3** — 即散射率 ~ 3 k_BT/ℏ

---

## 5. 温度依赖与 DC 电阻率

**关键观察：两通道是并联（电导相加），不是串联（违反 Matthiessen 规则）**

```
σ_DC = σ₀ + S/Γ = σ₀ + S/(α k_BT/ℏ) = a + b/T
⟹ ρ_DC = 1/(a + b/T)
```

| 样品 | a | b |
|------|---|---|
| x = 0.45 | 1.26 | 33.98 |
| x = 0.35 | 1.83 | 23.40 |

- 拟合范围：**200 K 降到 25 K**（SC 涨落出现前）
- 线性 T 散射观测到 ~40–50 K；低于 25 K，Γ 窄于 0.2 THz 无法分辨

---

## 6. 物理诠释：Nematic QCP + Fluctuations

作者提出 FTS 超导由**向列涨落**（NFMS，nematic fluctuation-mediated superconductivity）介导：

- **最佳掺杂接近 nematic QCP**（Mukasa et al. 2023）
- Islam & Chubukov 2024 理论预测：
  - 线性 ω 自能 → Planckian 散射 ✓
  - "Cold spots" 提供低 T 带内态 → 解释残余 σ₀ ✓
  - 超流密度呈"脏 BCS"行为，**S_δ/S_N ≤ 0.5**（杂质散射降低）

| 样品 | S_δ/S_N（测量）| NFMS 预测 |
|------|--------------|-----------|
| x = 0.45 | 0.53 | ≤ 0.5 ✓ |
| x = 0.35 | 0.30 | ≤ 0.5 ✓ |

注：干净 nematic QCP 预测 ω^(2/3)；观测到线性 T 归因于杂质效应修正

---

## 7. 与铜氧化物的类比

- FTS 相图 = 超导圆顶跨越 QCP，与铜氧化物镜像
- 线性 T 电阻率 = 铜氧 strange-metal 标志，首次在 FTS 的 THz 窄 Drude 通道中明确识别
- 并联通道分解此前在铜氧已做：Cooper (LSCO)、van Heumen (Bi-2201)
- **核心新意**：**超导凝聚的 spectral weight 完全来自 Planckian 通道的正常态权重** → 直接把 strange-metal 关联和配对联系起来

光谱形态类似：LCCO, LSCO, Sr₂RuO₄

---

## 8. 超流密度分析（3 种方法一致性）

1. 两流体模型拟合 S_δ
2. σ₂ν 二次外推至 ν=0
3. Ferrell-Glover-Tinkham sum rule: S_δ = S_N − S_U

关键发现：
- **S_δ 在 Tc 以上非零** → 超导涨落存在
- **S_δ(T→0) 略超 S(Tc+2K)** → Planckian 通道 = 凝聚体源头
- Dirty s-wave 拟合需 Tc₀ = 18 K (x=0.45) / 16 K (x=0.35)，高于实测 Tc → 暗示增强能隙（>3.53 k_BTc BCS 值）或非-BCS 临界行为

---

## 9. 关键引用

| 主题 | 引用 |
|------|------|
| 拓扑超导 | Yin 2015, Zhang 2018 Science, Wang 2018 Science |
| Nematic QCP 最佳掺杂 | **Mukasa et al. PRX 2023** [14] |
| FeSe/FeTe 质量增强最高 | Yin, Haule, Kotliar 2011 |
| 铜氧 Planckian | **Legros et al. 2019 Nat Phys** |
| NFMS 理论核心 | **Islam & Chubukov 2024** (arXiv:2412.07008) |
| LSCO 并联通道先例 | Cooper 2009 |
| 光谱比较 | LCCO (Tagay 2021), LSCO (Mahmood 2019), Sr₂RuO₄ (Wang 2021) |
| 原始 FTS 光学 | **Homes et al. 2011**（ε∞ = 4 来源）|

---

## 10. 承认的局限

1. **谱范围局限 0.2–3 THz**：低于 25 K 时 Drude 峰窄于 0.2 THz，无法追踪 Γ
2. **高于 40–50 K**：散射率超 3 THz，峰太宽
3. **Tc 附近超流密度的 T 依赖**：σ₂ν 二次外推"不正确"，需更低频率探测
4. 推荐后续：**横场 μSR**（Matsuura et al. 在 FeSe₁₋ₓSₓ 已做）
5. **σ₀ 微观起源未确定**：作者将其当作常数或极宽 Drude 处理
6. **Dirty-BCS 拟合需 Tc₀ ≠ 实测 Tc** → 模型不完全自洽
7. 清洁 nematic QCP 应给 ω^(2/3)，未观测到 → 需用杂质效应调和

---

## 11. 与我们研究的连接

### 直接连接
- **Paper A (Two-Channel Allen-Dynes)**：λ_sf 通道（自旋涨落介导配对）
- **Armitage 的窄 Planckian 通道**：同一批自旋/向列涨落在正常态的散射表现
- 两篇互补：Paper A 处理配对侧，Armitage 处理散射侧

### Anti-Sycophancy Protocol 注意
- **NFMS = 向列涨落介导超导**（nematic fluctuation），不是纯自旋涨落
- Paper A 里的 λ_sf 严格说是自旋涨落 → 需要区分"spin fluctuation" vs "nematic fluctuation"
- 向列 + 自旋常耦合（Pomeranchuk + AFM），但理论上可独立
- 不能把 Armitage 的 Planckian 通道直接等同于 Paper A 的 λ_sf —— **需要严格对应，避免挪用**

### 可能的修订点（Paper A 如果重审）
```
可以引用：Romero et al. Nat Phys 2026, α ≈ 3 Planckian scaling in FTS normal state
表述：independent support that a secondary (non-phonon) channel 
     contributes to normal-state transport in iron chalcogenides, 
     consistent with our λ_sf treatment in the pairing sector.
不可表述：Armitage's Planckian channel IS our λ_sf (过度声称)
```

### 对室温超导研究的启示
- **FeSe 族超导机制有"两通道"结构**：增加物理复杂度，但也给出新约束
- **NFMS（向列）**和 **AFM spin fluctuation** 是两个不同的 QCP 候选
- 如果要研究 FeSe 超导，需考虑向列自由度作为额外 knob
