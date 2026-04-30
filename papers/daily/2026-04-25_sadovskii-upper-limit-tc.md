# 精读笔记 — Sadovskii 2025: Upper limit for Tc in electron-phonon superconductors

**来源:** Sadovskii, M.V., "Upper limit for superconducting transition temperature in electron-phonon superconductors: very strong coupling", submitted June 24, 2025 (arXiv, cond-mat.supr-con)  
**年份:** 2025  
**线:** SC  
**日期:** 2026-04-25

## 核心方法论
- 综述近年来关于电子-声子超导体最高可达 Tc 的理论研究
- 从 Eliashberg-McMillan 理论出发，分析 λ → ∞ 极限下 Tc 的渐进行为
- 结合高压氢化物的实验数据验证理论预测

## 关键结果

1. **Allen-Dynes 强耦合极限：** Tc → (1/2π)·√(λ)·Ω₀ 当 λ ≫ 1
   - 这是 Eliashberg 理论的严格渐进结果
   - Ω₀ 是特征声子频率

2. **反绝热极限（anti-adiabatic limit）：** 当 ω_D/E_F → ∞，上限由原子常数和传导电子密度决定
   - Sadovskii 的早期工作 (2024, arXiv:2407.02742) 给出了 McMillan 理论下的上限估计
   - 这篇综述扩展到包含顶点修正和非 Migdal 区域

3. **氢化物验证：** 记录高 Tc（LaH10 ~250K, H3S ~200K）是 e-ph 机制能力的展示
   - 但当前记录仍远低于理论上限

4. **关键限制因素：**
   - Coulomb 伪势 μ*（典型值 0.10-0.15 显著压制 Tc）
   - 晶格不稳定性限制了 λ 的实际可达值
   - 声子频率有天然上限（取决于原子质量）

## 与已有工作的区别
- Sadovskii 2021 (arXiv:2106.xxxxx) "Limits of Eliashberg Theory" 是更早的综述
- 2024 版给出了 McMillan 框架的简单估计
- 2025 版是最完整的综述，包含了最新氢化物数据和强耦合理论发展

## 启发的新想法
**[假设] 300K 可能需要 λ > 3 + 低 μ* + 高 ω_log 的组合，Allen-Dynes 渐进公式给出的 Tc ∝ √λ·Ω₀ 意味着即使 λ = 5，也需要 Ω₀ > 1200K。** 这与我们在 Night 38 计算的 H24 cage 阈值（λ_anh ≥ 2.5 at μ*=0.10）一致。Sadovskii 的分析为这些阈值提供了独立的理论支撑。

**[可验证]** 我们可以将 Sadovskii 的上限公式与我们的 Two-Channel AD 框架进行交叉比较：Sadovskii 给出的绝对上限 vs 我们的 family-specific corrections，看是否一致。

## 与研究的关联
★★★ 核心参考文献。直接回答"300K 在 e-ph 框架内是否理论上可能？"的问题。答案是：可能，但需要极端参数组合。

## 数值/公式
- Allen-Dynes 强耦合极限: Tc ≈ 0.183·√(λ·⟨ω²⟩) [当 λ ≫ 1]
- McMillan 理论上限: Tc_max ∝ (ℏ²n_e^{2/3})/(m_e·k_B) （取决于电子密度）
- 典型 λ 范围: H3S ≈ 1.7-2.2, LaH10 ≈ 2.5-3.5
- μ* 效应: μ* 从 0.10 → 0.15 可降低 Tc 约 20-30%
