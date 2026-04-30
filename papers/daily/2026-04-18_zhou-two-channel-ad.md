# Zhou 2026: Two-Channel Allen-Dynes Framework

**arxiv:** 2604.04719 | **Authors:** Jian Zhou

## 核心方法论

两通道 Allen-Dynes 框架：
```
Tc = min(T_pair, T_phase)
```

**通道 1 — Pairing:**
标准 Allen-Dynes + spin-fluctuation 耦合：
- λ_eff = λ_ph + λ_sf
- ω_log^eff = exp[(λ_ph·ln(ωph) + λ_sf·ln(ωsf)) / (λ_ph + λ_sf)]
- T_pair = (ωlog/1.2) × exp[-1.04(1+λ)/(λ - μ*(1+0.62λ))]
- μ* = 0.10 (default), 0.13 for V

**通道 2 — Phase coherence:**
Peotta-Törmä 几何超流刚度：
- D_s = D_conv + D_geom
- D_geom ∝ tr(g(k)) · |Δk|² · f'(εk)  (quantum metric!)
- T_BKT = (π/2)(ℏ²/kB)Ds

**No-go 定理:** 量子度规 **不能** 直接修改 s-wave 的 e-ph 耦合！
- 原因：Debye 波矢 qD ≈ π/a = BZ 边界
- 声子和 Coulomb 通道探测相同动量范围 → Bloch overlap 同等压制
- d-wave 差分压制: δF/F₀ = 0.7% (三带 Emery 模型) → 可忽略

## 关键结果

### Tier 1 盲预测（19 材料，无 Tc 输入）
- R²_log = 0.961, 19/19 within 2x
- MAE = 5.6 K
- **H₃S: 203K → 204K (1.00x)**
- LaH₁₀: 250K → 183K (0.73x) — AD 对 λ>2.5 不准
- YH₆: 224K → 173K (0.77x)

### Tier 2 交叉验证（22 材料，λ_sf 用 Tc 拟合）
- FeSe/SrTiO₃: 65K → 66K (1.01x)
- LSCO: 38K → 41K (1.07x)
- Bi-2212: 85K → 88K (1.03x)

### Quantum metric 与 Tc 的关系
- tr(g) 与 Tc 相关 (Pearson r=0.56, p=10⁻⁴)
- 但因果链是 **间接的**: large tr(g) ↔ flat bands/vHs ⇒ high N(EF) ⇒ high Tc
- tr(g) 是 N(EF) 的代理指标，不直接贡献 pairing

### 7 个 Tc > 200K 候选材料（Table II）
- 包括 Eliashberg 修正后部分超过 300K

## 与已有工作的区别
- 首次统一 phonon + spin-fluctuation 双通道在 AD 框架内
- 首次给出 quantum metric no-go 定理（对 s-wave）
- 覆盖 5 个数量级的 Tc (0.4K-250K)

## 启发的新想法
**★ 自旋涨落通道对非常规超导体是主导的。** Fe-based, cuprate 系列中 λ_sf >> λ_ph。但对 hydrides 系统 λ_sf ≈ 0，纯 e-ph。这意味着 300K 的纯 phonon 路径需要 λ>3.3 + ω_log>1200K（我们 Night 33 的结论），而加入 spin-fluctuation 通道则有更多自由度。

## 与研究的关联
- 对 SC latest_state 的 AD 公式准确性有直接检验
- LaH₁₀ 偏低 27% → AD 对 λ=3.5 确实不够，需要 full Eliashberg
- No-go 定理排除了 quantum metric → Tc 的直接机制 → flat-band SC 不是 300K 捷径
- 7 个 >200K 候选值得追踪

## 数值/公式
- μ* = 0.10 (default)
- R²_log(blind) = 0.961, MAE = 5.6K
- Quantum metric anisotropy: δF/F₀ < 0.8% for s-wave and d-wave
- tr(g) ↔ Tc: Pearson r = 0.56
