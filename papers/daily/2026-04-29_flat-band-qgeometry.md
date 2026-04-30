# Correlation Lengths of Flat-Band SC from Quantum Geometry
**arXiv:2601.12969** | Elden, Iskin | Jan 2026

## 核心方法论
- 在 all-flat-band 系统中研究三种超导长度尺度:
  1. 二体束缚态尺寸 (two-body bound-state size)
  2. Cooper 对平均尺寸 (average Cooper-pair size)
  3. 零温相干长度 (zero-T coherence length)
- 模型: Creutz ladder 和 χ lattice (two-band Hubbard, perfectly flat bands)
- 理论框架: BCS-BEC crossover + Gaussian fluctuations + localization tensor

## 关键结果
- **对尺寸 (pair size) 在弱耦合极限保持有限且小**, 由量子度规 (quantum metric) 控制
- **相干长度 (coherence length) 行为完全不同**: 在稀释极限和绝缘体附近发散
- **核心发现: 在 flat-band 超导体中, pair size 和 coherence length 是根本不同的物理量**
- 调和了此前关于 flat-band 超导长度尺度的争论 (Törmä 组 vs 其他)

## 与已有工作的区别
- 此前 Peotta-Törmä (2015) 提出 ξ = √(ξ_BCS² + l_qm²), ξ 有下界 l_qm
- 反方 (Ref [16,24]) 认为 ξ 与量子度规无关, 无下界
- **本文调和**: pair size 确实由量子度规决定(有下界), 但 coherence length 可以发散(无下界)
- 两个量度量了不同物理: pair size = 对的空间延展, ξ = 超流响应的空间范围

## 启发的新想法
**[假设]** 在 RTSC 材料设计中, 如果能找到 large quantum metric + flat band 的 3D 材料, pair size 小但 Tc 高可能同时实现. Twisted bilayer graphene 的量子度规已知, 可以作为基准检验.

## 与研究的关联
- SC 线 pivot 方向: flat-band 超导的理论基础
- 与已读的 Tupitsyn+2026 (numerically exact flat-band SC) 互补: 那篇数值, 这篇解析
- 量子几何框架为非 BCS 机制提供数学基础

## 数值/公式
- ξ_pair ~ √(Tr g_μν) 在 flat-band 极限 (g_μν = quantum metric tensor) [arXiv:2601.12969]
- ξ_BCS → 0 但 ξ_pair → l_qm (有限) 在弱耦合 flat-band [arXiv:2601.12969]
- Coherence length ξ → ∞ 在稀释极限 (n→0) [arXiv:2601.12969]
