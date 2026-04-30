# Kinetic instability and superconductivity in Li₂AuH₆ and Li₂AgH₆ at ambient pressure
- **arXiv:** 2604.12367
- **Authors:** Yucheng Ding, Haoran Chen, Junren Shi
- **Year:** 2026
- **Line:** SC

## 核心方法论
用 **path integral molecular dynamics (PIMD)** 模拟在 80K 下检验 Li₂AuH₆/Li₂AgH₆ 的动力学稳定性。关键区分：动力学稳定性（phonon dispersion）≠ 运动学稳定性（MD 下结构是否坍塌）。用 **stochastic path-integral approach (SPIA)** 非微扰地计算 Tc。

## 关键结果
1. **Li₂AgH₆**: MD 和 PIMD 下都坍塌 → 完全不稳定
2. **Li₂AuH₆**: 
   - MD (经典): 所有原子在平衡位振动，看似稳定
   - PIMD (量子): H 原子开始扩散！**量子涨落导致动力学不稳定**
   - Li-Au 子晶格保持 fluorite 结构，但 H 部分二聚为 H₂ 分子（23.6% H 原子二聚）
   - H-H RDF 在 0.74 Å 处有尖峰（恰好是 H₂ 键长）
3. **SPIA 预测 Tc = 22K**，远低于之前 80-140K 的预测
4. λ(0) = 0.838，远低于文献值 2.10-2.84
5. 原因：H 子晶格坍塌 + H₂ 二聚 → 费米面 DOS 大幅降低

## 精确数值/公式
- Li₂AuH₆ 原胞晶格参数: 4.71 Å (优化后)
- Li₂AgH₆ 原胞晶格参数: 4.62 Å
- λ(0) = 0.838 (SPIA) vs 2.10-2.84 (SSCHA 文献值)
- ν̄₂ = 758 K (phonon 平均频率, 与文献 724-982K 接近)
- Tc = 22 K (SPIA) vs 80-140 K (文献)
- PIMD: Nb=16 beads, 80K, 6ps, 3×3×3 supercell (243 atoms)

## 与研究的关联
**对 ambient-pressure hydride SC 方向的重要警告**。我们 SC 研究追踪氢化物路径，这篇论文用最严格的方法（PIMD+SPIA）证明了：
1. 之前被寄予厚望的 Li₂AuH₆ 在 ambient pressure 下根本不是 kinetically stable
2. 量子效应（H 的零点运动）是杀手——经典 MD 看不出来
3. SPIA 方法不需要假设平衡位置，可以处理扩散原子——这是我们评估非传统超导体时需要的工具

## 启发的新想法
**假设**: 所有声称 ambient-pressure Tc > 80K 的 SM₂-TM-H₆ 族氢化物都可能遭受类似的 H 子晶格不稳定性。**验证方法**: 对每个候选材料做 PIMD 模拟（而不仅仅是 phonon 计算），特别关注 H-H RDF 是否出现 0.74Å 峰。如果出现，真实 Tc 可能被高估 5-7 倍。这可以排除大量虚假候选材料，集中资源在真正稳定的候选者上。
