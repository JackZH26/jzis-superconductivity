# Kimura+2026: Metal Atom (Dis)Order and Superconductivity in YCaHₙ (n=8-20) High-Pressure Superhydrides

**arXiv:** 2604.17712  
**Authors:** Masashi W. Kimura, Seong Won Jang, Nisha Geng, Eva Zurek  
**Date:** 2026-04-20

## 核心方法论
- DFT + evolutionary algorithm (XtalOpt) CSP 搜索 YCaHₙ (n=8-20) 在 100-300 GPa
- Isotropic Eliashberg equations (IsoME v1.0.4) 计算 Tc
- Allen-Dynes modified McMillan + strong-coupling/shape corrections
- 考虑 configurational entropy Sconfig 对稳定性的影响
- RS5 semi-empirical fit 作为 Tc 初步筛选

## 关键结果

### YCaH₈ — 金属原子无序 + Fermi level tuning
- **多种 nearly isoenthalpic 构型** — metal atom 排列不同但焓差极小 → 配置熵 Sconfig 对稳定性关键
- P4/mmm YCaH₈: **Tc = 149 K** @ 180 GPa (μ*=0.13, Eliashberg)
- Cmmm YCaH₈: **Tc = 170 K** @ 180 GPa (μ*=0.13, Eliashberg)
- 机制: Y+Ca 等摩尔混合将 Fermi level 调至 DOS 峰值 → 增强 Tc
- Y(3 价电子) vs Ca(2 价电子): 差异产生 doping 效应

### YCaH₁₂ — 无序 + Tc 范围极广
- 也预测为无序态
- **有序变体 Tc 范围 105-253 K** @ 200 GPa → 掺杂可增强也可剧烈降低 Tc
- 对比母体化合物，doping 效果非单调

### YCaH₁₈ 和 YCaH₂₀
- 各只有一种动力学稳定的超氢化物
- 归因于二元母体结构的差异（YH₉ vs CaH₆ 结构类型不同）

### 热力学稳定性
- 100 GPa: YCaH₈, YCaH₉, YCaH₁₅, YCaH₁₇ 稳定
- 150 GPa: YCaH₈, YCaH₁₇, YCaH₁₂ 稳定
- 200-300 GPa: YCaH₈, YCaH₁₂, YCaH₁₁ 稳定

## 与已有工作的区别
- 首次系统考虑 Y-Ca 体系全氢含量 (n=8-20) + 配置熵
- 之前的 Y-Ca 研究 [Liang+2019, Huo+2022, Shi+2021, Liang+2023] 未考虑 Sconfig（仅 n=6 例外）
- 发现 YCaH₈ 和 YCaH₁₂ 的 metal disorder 特征 → 对高熵超氢化物有启示

## 启发的新想法
**假设:** MSc₂H₂₄ family (如 CeSc₂H₂₄, LaSc₂H₂₄) 中 metal disorder 是否同样重要？如果 M/Sc site 有 near-isoenthalpic 排列，则 Sconfig 可能显著降低合成压力。
- 可验证: 对 CeSc₂H₂₄ 做 site permutation 计算，比较不同 metal ordering 的焓差

**假设:** Fermi-level tuning through equimolar metal mixing → 可以系统搜索使 EF 落在 DOS 峰的 ternary 组合
- YCaH₈ 的 Tc 从 parent 约 100K 跳到 170K，纯靠 EF tuning

## 与研究的关联
- **直接关联 300K 设计:** YCaH₁₂ 最高 253K @ 200 GPa — 仍低于 300K 但验证了 EF tuning 策略的有效性
- **方法论启发:** isotropic Eliashberg (IsoME) 是当前标准工具，可用于我们的 AD framework 验证
- **AD saturation 验证:** 论文用 Allen-Dynes + Eliashberg 比较 → 可检查我们的 AD saturation 效应

## 数值/公式
- YCaH₈ P4/mmm @ 180 GPa: λ 和 ω_log 需要从 SI 获取 [UNVERIFIED]
- Tc(AD, μ*=0.10/0.13): 报告了对比 Eliashberg 结果
- 结构类型: sodalite H₂₄ cage (Im-3m), H₂₉ cage (P6₃/mmc), H₃₂ cage (Fm-3m)
