# Two-Channel Allen-Dynes Framework for Superconducting Critical Temperatures
**arXiv:2604.04719** | April 2026
**Authors:** (not specified in abstract listing)

## 核心方法论
提出双通道 Allen-Dynes 框架：Tc = min(T_pair, T_phase)
- **Channel 1 (配对):** 标准 Allen-Dynes 公式 + 自旋涨落耦合 λ_sf
- **Channel 2 (相干):** Peotta-Törmä 超流刚度（量子度量贡献）

关键公式：
- λ_eff = λ_ph + λ_sf
- ω_log^eff = exp[(λ_ph·ln(ω_ph) + λ_sf·ln(ω_sf))/(λ_ph + λ_sf)]
- T_pair = (ω_log/1.2)·exp[-1.04(1+λ)/(λ-μ*(1+0.62λ))]

## 关键结果
1. **盲预测 19 种材料：R²_log = 0.961，19/19 在 2× 误差内，MAE = 5.6 K**
2. **量子度量 no-go 定理：** 对 s-wave 和准各向同性 d-wave，量子度量不能修改 e-ph 耦合——因为 Debye 动量转移 q_D ≈ π/a 确保声子和库仑通道的 Bloch 重叠抑制相同
3. d-wave 各向异性差异仅 0.7%（三带 Emery 模型）
4. 量子度量 tr(g) 与 Tc 相关（r=0.56）——但仅作为带结构诊断指标（平带/vH/nesting → 高 N(EF) → 高 Tc）
5. **H₃S 盲预测：203 K → 204 K（1.00×）！** LaH₁₀：250 K → 183 K（0.73×，因 λ>2.5 超出 AD 适用范围）
6. 识别 7 种候选材料 Tc > 200 K

## 与研究的关联
- **直接挑战我们的 AD→Eliashberg 校正方法！** 该论文指出 λ>2.5 时 AD 失效，需要完整 Eliashberg
- 双通道框架为我们的 family-specific 校正因子提供理论基础：不同家族的 ω_sf/ω_ph 比不同
- ω_log^eff 的权重公式可以解释为什么 H₈ 和 H₁₂ 家族的 AD/Eliashberg 比不同
- **no-go 定理重要：** 排除了量子度量直接增强 e-ph 的路径，聚焦到传统 Eliashberg 机制

## 启发的新想法
**假设：** 双通道 ω_log^eff 权重可以统一解释我们观察到的 family-specific AD→Eliashberg 偏差。如果 H₈ 族有更宽的双峰 α²F（有效 ω_sf 分量），那么用单通道 ω_log 会低估有效频率，导致更大的 AD/Eliashberg gap。**可验证：** 用 Kimura+2026 数据检验双通道公式是否能消除 family-specific 校正的需要。

## 数值/公式
- 盲预测 R² = 0.961 (19 材料)
- H₃S: λ_ph 来自隧穿谱，Tc_pred = 204 K vs Tc_exp = 203 K
- LaH₁₀: λ = 3.5，Tc_pred = 183 K vs Tc_exp = 250 K (AD 失效区)
- YH₆: Tc_pred = 173 K vs Tc_exp = 224 K (同上)
- μ* = 0.10（除 V 用 0.13）
- d-wave 各向异性修正 < 0.8%
