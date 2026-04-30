# Lucrezi et al. — Temperature and Quantum Anharmonic Lattice Effects on LuH₃
**arXiv: 2304.06685 | Nat Commun 15, 441 (2024)**

## 核心结论
- Fm-3m LuH₃ 在谐振近似下有大量虚频模（整个 BZ）
- SSCHA + 温度效应: T > 200K + p ≈ 2 GPa 可稳定 Fm-3m 相
- Migdal-Eliashberg Tc ≈ 50-60K @ 2.8 GPa（用 SSCHA 校正声子）
- 掺杂（空穴或电子）均降低 Tc → 排除常规 e-ph 机制解释 RTS

## 方法论（极其重要 — SSCHA + ME 完整流程）
1. **SSCHA 计算流程**:
   - 给定晶格常数 a → DFT 超胞计算（位移构型采样）
   - 随机采样多个连续系综（stochastic ensembles）
   - 最小化自由能 → 自洽谐振力常数
   - ★ 注意: p(SSCHA) > p(DFT)，因为零点运动增加内部压力
2. **p-T 相图构建**: 扫描 a 和 T → 每个点做 SSCHA → 判断是否有虚频
3. **Tc 计算**: SSCHA 声子 → α²F(ω) → isotropic ME → Tc
4. **掺杂**: rigid band shift 近似

## 关键数值
- LuH₃ Fm-3m: 谐振有大量虚频 → SSCHA @ T > 200K 稳定
- λ (SSCHA 校正后) 未显式给出 — 但 Tc ≈ 50-60K 可反推 λ ≈ 0.8-1.2
- a = 5.040 Å → p_SSCHA ≈ 2.1 GPa (T=0K), 2.8 GPa (T=200K)

## 启发的新想法
1. **★★ SSCHA 自洽压力 vs DFT 压力差异**: p_SSCHA > p_DFT，这意味着零点运动有效地增加了内部压力。对于设计新材料，DFT 预测的稳定压力可能偏低。
2. **假设**: 对于 LuH₃ 这样需要 T > 200K 才能稳定的材料，Tc < T_stability → 材料在超导态不稳定。这是一个设计约束: T_stability < Tc 才有用。
3. **对比 LaH₁₀**: LuH₃ 稳定后 λ 较小 → Tc 低。关键区别: LuH₃ 的 H 原子在八面体位，LaH₁₀ 的 H 形成 clathrate 笼。

## 与研究的关联
- SSCHA 方法论的完整参考实现 — 可用于我们的框架验证
- ★ 关键教训: "谐振不稳定" ≠ "SSCHA 不稳定"，但也不保证高 Tc
- LuH₃ 案例: 即使 SSCHA 稳定，如果原始虚频不够"软"(不贡献足够的 e-ph)，Tc 仍然低
- 与 LaH₁₀ 对比: clathrate 氢笼结构 >> fcc 氢填充结构

## 精确数值
- Tc ≈ 50-60K @ 2.8 GPa [Lucrezi+2024, DOI:10.1038/s41467-023-44326-4]
- T_stability > 200K @ 2 GPa, > 80K @ 6 GPa
