# 精读笔记 — Geisler et al. "Towards the discovery of high critical magnetic field superconductors"

**arXiv:** 2601.21044 | **年份:** 2026
**作者:** Benjamin Geisler, Philip M. Dee, James J. Hamlin, Gregory R. Stewart, Richard G. Hennig, P. J. Hirschfeld

## 核心方法论

构建包含 7300+ 电子-声子配对超导体的第一性原理数据库，计算临界磁场 Hc, Hc1, Hc2。方法流程：
1. DFT (VASP + PBEsol) 优化结构 → 费米面 + 费米速度 ⟨vF²⟩
2. α²F(ω) 谱函数 → isotropic Eliashberg 方程 → Tc + Δ(0)
3. 干净极限公式：ξ(0) = ℏ√⟨vF²⟩/(πΔ(0)), λL(0) = √(3/(μ₀e²n(EF)⟨vF²⟩))
4. 电声耦合修正：λL → λL√(1+λ_e-ph), ξ → ξ/(1+λ_e-ph)
5. GL 参数 κ = λL/ξ → Type I/II 分类 → Hc, Hc1, Hc2

## 关键结果

1. **Hc2 核心公式**：Hc2 = Φ₀/(2πξ²) = π²/(2eℏ) · Δ²/⟨vF²⟩
   - 高 Hc2 需要：大 Δ（高 Tc）或低 vF（重费米子效应）
   - 两者二次方进入 → 平衡策略：中等 Tc + 低 vF 可能优于高 Tc + 高 vF

2. **Type I 超导体数量惊人**：
   - 1626 Type-I vs 801 Type-II (Tc > 1K)，与常识相反
   - 原因：干净极限计算；真实材料中杂质会增大 κ → 推向 Type-II
   - 更大晶胞倾向支持更高临界场和 Type-II 行为

3. **强耦合修正至关重要**：
   - BCS gap ratio Δ/kBTc 分布峰值在 1.764 但尾巴延伸到 3.55（2倍 BCS 值）
   - Nb: Hc2 从 0.072T (BCS) → 0.321T (Eliashberg)，提升 4.5 倍
   - 需要同时包含 gap 强耦合修正和电声耦合的有效质量重整化

4. **顶级 Hc2 材料**：
   - Cr₄NbRe: Hc2 ≈ 67T（F̄43m 结构）
   - LiMoN₂: Hc2 ≈ 48T（R3m 结构，ξ = 2.62 nm）
   - Nb₃Pt: Tc ~ 13K, Hc2 ~ 10T（已知超导体）

5. **关键发现**：高 n(EF) 对 Tc 有利，但不保证高 Hc2。vF 和 n(EF) 的 Pearson 相关系数仅 0.66。

## 与已有工作的区别

首次系统计算 7300+ 材料的临界磁场数据库。此前所有数据驱动方法都只关注 Tc 预测，忽视了 Hc2 这个同样重要的技术参数。揭示了 Tc 和 Hc2 的解耦——高 Tc 不保证高 Hc2。

## 启发的新想法

★ **假设：在 SC 研究中，与其预测 Tc，不如预测 Hc2。** 理由：
1. Hc2 由 Δ²/vF² 决定，两个量都可从 DFT 较准确获得
2. Hc2 对技术应用更关键（需要 >10T 用于磁体应用）
3. 本文的框架可直接应用于镍基超导体的 Hc2 预测

**具体实验方向**：计算 LNO 在不同压力下的 vF（已有 DFT 数据），结合实验 Tc/gap 数据，预测 Hc2(P) 曲线。

## 与研究的关联

★ **对 Night 28 转向的直接支持**：本文正是"预测非 Tc 的可测量性质"的范例。Hc2(P) 预测比 Tc 预测更 tractable，且有明确的实验验证路径。

## 数值/公式

- Hc2 = π²/(2eℏ) · Δ²/⟨vF²⟩
- Hc2^BCS(Tc, vF) = π²/(2eℏ) · (1.764 kBTc)²/vF²
- κ = λL/ξ, Type I/II 界线 κ = 1/√2
- 电声修正：vF → vF/(1+λ_e-ph), n(EF) → n(EF)(1+λ_e-ph)
- Nb: λL = 19→27 nm, ξ = 68→32 nm, κ = 0.28→0.85 (after renorm)
- 数据库规模：7300+ 材料，覆盖 Hc 4 个数量级
