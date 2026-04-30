# Bypassing the lattice BCS-BEC crossover in strongly correlated superconductors: resilient coherence from multiorbital physics
- **作者:** Niklas Witt et al.
- **来源:** arXiv:2310.09063, npj Quantum Materials 9, 100 (2024)
- **年份:** 2023/2024
- **研究线:** SC
- **精读日期:** 2026-04-09

## 核心贡献（一句话）
在 A₃C₆₀（碱金属掺杂富勒烯）多轨道模型中证明，强关联+多轨道效应可以绕过晶格 BCS-BEC crossover 限制，实现短相干长度但高相位刚度的"弹性"超导态。

## 关键方法论
- **多轨道 Hubbard 模型**: A₃C₆₀ 的三重简并 t₁u 轨道
- **新理论框架**: 在强关联下计算超导体的两个基本长度尺度——相干长度 ξ₀ 和 London 穿透深度 λ_L
- **关键创新**: 常规 BCS-BEC crossover 中，增强配对 → 电子局域化 → 相位刚度下降 → Tc 被限制。但多轨道效应打破这个限制：
  - 单轨道: 配对增强 → Cooper 对收缩 → 相位刚度降低 → Tc dome
  - 多轨道: 配对增强 → Cooper 对收缩 → 但跨轨道隧穿保持相位刚度 → Tc 无 dome 上升！
- **DMFT + 超流密度计算**: 完整的多体框架

## 主要结果
1. **核心发现**: 多轨道超导体可以有短 ξ₀ 和强 ρ_s（超流密度），违反单轨道 BCS-BEC 图像
2. Tc 随配对作用单调上升（无 dome），不受 BCS-BEC crossover 限制
3. 关键机制：轨道间隧穿在实空间保持长程相位相干，即使单轨道内 Cooper 对已经局域化
4. A₃C₆₀ 是这种"弹性超导"的实验实现

## 与我们研究的关联
- **对 La₃Ni₂O₇ 的启示**: LNO 是双轨道系统（dz² + dx²-y²），满足多轨道条件！自掺杂分子 Mott 模型中，bonding 轨道的 Cooper 对可能通过与 antibonding 轨道的隧穿保持相位刚度。
- **解释为什么 LNO 的 Tc 可以这么高**: 如果 LNO 处于 BCS-BEC crossover 附近（Schlömer+2023 DMRG 建议），多轨道效应可能是绕过 crossover 限制达到高 Tc 的关键。
- **SC latest_state 中的 BEC-BCS 讨论**: 我们记录了 "BEC-BCS crossover 理论支持 >300K T_BKT"，但标注为"理想化模型"。这篇论文提供了更精确的物理机制。
- **预测能力**: 如果 LNO 确实利用了多轨道弹性效应，那么 Tc 可能远超目前的 80K 上限——关键是找到增强配对作用的方法（更大 J⊥？更优 ΔJT？）

## 潜在问题/局限
- A₃C₆₀ 是分子晶体，带宽 ~0.5 eV，与 LNO 的 ~2 eV 差异大
- DMFT 方法在准二维系统（如 LNO）的适用性有限
- "无 dome" 预测需要在 LNO 的实际参数区间验证
- 没有直接应用到镍酸盐

## 关键数值
- A₃C₆₀: Tc ~40K (实验), ξ₀ ~几个晶格常数 (极短)
- 多轨道增强因子: ρ_s 比单轨道预期大 ~5-10×

## 启发的新想法
- **假设**: La₃Ni₂O₇ 的 dz² + dx²-y² 双轨道结构提供了 Witt 等人描述的"弹性超导"通道。如果在最优 ΔJT 处，两个轨道的 Cooper 对相位刚度相互增强，则理论 Tc 上限可能远超 80K。定量地：用双轨道 t-J 模型的超流密度公式计算最优 ΔJT 处的 T_BKT。
- **可验证**: 从 Wang+ 的 Wannier 参数构造双轨道有效模型，用 DMRG 或 variational Monte Carlo 计算不同 ΔJT 下的超流密度。
