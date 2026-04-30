# Charge-4e/6e superconductivity and chiral metal from 3D chiral superconductor
- **arXiv:** 2604.12328
- **Authors:** Chen Lu, Yu-Bo Liu, Zhiming Pan, Fan Yang
- **Year:** 2026
- **Line:** SC

## 核心方法论
用 Ginzburg-Landau 自由能分析 + Monte Carlo 模拟，系统研究了 **3D 立方 Oh 点群**下手征超导的 vestigial（残余）相。关键创新：不是 2D BKT 机制，而是 3D 传统热涨落驱动。

对 Eg IRRP（二分量序参量 ψ₁, ψ₂）：自由能第四阶展开给出 β₂ < 0 时的手征态 (1:i)。低能有效哈密顿量分解为全局相 θ（XY 模型，刚度 ρ）和相对相 φ（Z₄ 各向异性 Ising 型，刚度 κ）。

对 T₂g/T₁u IRRP（三分量）：手征态 (1:ω:ω²)，ω=e^{2πi/3}，产生 charge-6e 超导！

## 关键结果
1. **3D vs 2D 相图拓扑完全不同**：3D 四临界点（tetracritical point），2D 三重点（triple point）
2. **κ ≪ ρ**：相对相先失序 → charge-4e/6e SC（TRS 恢复但 U(1) 保留）
3. **κ ≫ ρ**：全局 SC 先消失 → 手征金属（TRS 保持破缺）
4. **T₂g/T₁u 特有 charge-6e SC**：Δ₆ₑ ~ ψ₁ψ₂ψ₃，磁通量子化 hc/6e
5. MC 模拟确认：θ 场 3D XY 普适类，φ 场 3D Ising 普适类

## 精确数值/公式
- Eg: F⁽⁴⁾ = β₁(|ψ₁|²+|ψ₂|²)² + β₂|ψ₁*ψ₂-ψ₂*ψ₁|²
- T₂g: F⁽⁴⁾ = (β₁+β₂)Σ|ψa|⁴ + 2β₂Σψa*²ψb² + 2(β₁+β₃)Σ|ψa|²|ψb|²
- Z₄ 各向异性强度: A = -2β₂ψ₀⁴ (Eg), A = 2β₂ψ₀⁴ (T₂g)

## 与研究的关联
**★ 直接回应我们的 3D vs 2D 困境！** 我们 SC 研究 Night 30 的核心发现是 BKT 杀死 2D 平带 SC。这篇论文从 GL 理论严格分析了 3D 情况下 BKT 为何不相关——3D 相变由传统热涨落而非涡旋解绑驱动。但更重要的是：**3D 允许的 vestigial 相结构比 2D 丰富得多**，特别是 charge-6e SC 仅在 3D 的 T₂g 表示中出现。这为我们设计 3D 平带超导材料提供了新的序参量选择。

## 启发的新想法
**假设**: 在 pyrochlore 3D 平带超导体中，如果配对对称性属于 T₂g IRRP，那么在 Tc 以上可能存在一个 charge-6e 残余超导相，其 Tc_6e > Tc_2e。可通过磁通量子化实验验证（hc/6e vs hc/2e）。这意味着 **300K 的 charge-6e 比 300K 的 charge-2e 可能更容易实现**，因为 vestigial 相可以在 primary SC 之上存在。
