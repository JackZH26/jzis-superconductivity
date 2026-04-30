# Ding+2025: Anharmonicity and Coulomb pseudopotential effects on YH₆ and YH₉

**arxiv:** 2507.03383 | **DOI:** 10.1103/8y74-91v2 | **Published:** PRL (2025)
**Authors:** Yucheng Ding, Haoran Chen, Junren Shi (Peking Univ.)

## 核心方法论

SPIA（Stochastic Path-Integral Approach）— 比 SSCHA 更一般化的非微扰方法：
1. 用 ab initio PIMD (path-integral MD) 采样离子构型 R(τ)
2. 对每个构型计算电子 Green 函数 G[R(τ)]
3. 从散射 T 矩阵的涨落提取有效电子-电子相互作用
4. 求解 Bethe-Salpeter 方程 → 各向同性 Eliashberg 方程

**关键创新：μ* 重正化**
```
1/μ*(N) = 1/μ* + ln(νph/ωN)
```
其中 N 是 Matsubara 频率截断，νph = 2518 K 是声子截断频率。此修正在以前的 YH₆/YH₉ 计算中被忽略！

## 关键定理/结果

### YH₆ (Im-3m, 165 GPa, 220K)
- SPIA: λ(0), λ(1), λ(2) 相比 DFPT 显著降低（与 SSCHA 结果一致）
- 平均声子频率 ν̄₂ 上升
- **Tc(SPIA + μ* renorm) = 212 K** ← 与实验 ~220 K 一致！
- DFPT + 无 renorm: Tc 过高 >260 K
- SSCHA + 无 renorm: Tc 仍过高 ~260 K

### YH₉ (P6₃/mmc, 255 GPa, 240K)
- SPIA: λ(0) 强烈压低，λ(m≥2) 增强
- ν̄₂ 显著增强
- **Tc(SPIA + μ* renorm) = 240 K** ← 与实验完美一致！

### μ* = 0.11 (GW 方法确定)

## 与已有工作的区别
- 之前 SSCHA 结果仍高估 YH₆ Tc 约 20K
- 本文证明问题不在 anharmonicity 不够，而在 **μ* 的频率截断重正化被忽略**
- SPIA 可以处理扩散性原子（SSCHA 不行），但此处两者结果一致

## 启发的新想法
**★ μ* renormalization 是我们 SC 研究的关键缺失因素！** 我们的 modified Allen-Dynes 公式用固定 μ*=0.13，但 Eliashberg 方程中 μ* 应随频率截断变化。对高 λ 体系（λ>2），这个修正可能超过 20K。我们需要在 Night 34 实验中加入此修正。

## 与研究的关联
直接回答 SC latest_state 的 #1 优先级："Verify remaining DFT parameters"。虽然本文未给出完整的 λ/ω_log 表（需查 Table 1），但确认：
- YH₆ 的 anharmonic λ 比 DFPT 低（估计 ~20-30% 降低）
- ω_log 因 anharmonicity 而上升
- 关键变量不是 λ/ω_log 本身，而是 **μ* 如何定义和截断**

## 数值/公式
- μ* = 0.11 [GW: Ref.mustar_GW]
- νph = 2518 K
- Tc(YH₆, SPIA) = 212 K (expt: ~220 K)
- Tc(YH₉, SPIA) = 240 K (expt: ~240 K)
- PIMD: 16 beads, 3ps, 0.5fs timestep
- Supercell: YH₆ = 3×3×4 (252 atoms), YH₉ = 3×3×2 (360 atoms)
