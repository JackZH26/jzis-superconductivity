# Rademaker et al. 2021 — Enhanced superconductivity in FeSe/SrTiO₃ from forward scattering phonons and spin fluctuations

**arXiv:** 2101.08307 | **Journal:** PRB 103, 144504 (2021) | **Line:** SC

## 核心方法论
- 两带 Hubbard 模型 + 长程 e-ph 相互作用
- **完全自洽** FLEX + Migdal-Eliashberg 计算（自旋涨落谱自洽决定）
- 前向散射声子: g(q) = g₀ exp(-|q|/q₀), q₀a = 0.1（动量空间极度集中）
- 关键: Hartree 移位自洽影响 incipient band 位置

## 关键定理/结果
1. **SF alone**: Tc ≈ 46.8 K (U=7t), incipient s± 配对
2. **SF + 前向声子**: Tc 可达 ~115 K (U=7t, λ_m≈0.23), 线性增强
3. Δ/Tc 比: 1.90 (SF only) → 2.23 (SF+phonon)
4. **对称性**: 高 U → s±; 中间 U → d-wave; U=0 → s-wave

## 与已有工作的区别
- 之前的工作 (Johnston 2016) 未做全自洽 FLEX+ME
- 自洽 Hartree 移位改变了 incipient band 的有效位置，定性改变结论
- 首次证明 SF 和前向声子可以"cooperative"增强而非竞争

## 与研究的关联
★ **直接关联 CDW-SF 多通道课题**: 证明多通道增强是可能的
- 关键区别: 前向声子 ≠ CDW boson（前向声子不降低 ω_log）
- 但证明了 k-dependent 相互作用的各向异性效应很重要
- BSE 方法 (Yamakawa-Kontani) vs FLEX+ME 的对比是下一步

## 启发的新想法
**假设**: CDW boson 的有害效应（降低 ω_log）可以通过 k-dependent 各向异性配对来部分缓解——类似前向声子的"选择性"增强 hot spots 而不拖低全局 ω_log。可以用 2-boson FLEX+ME（SF + CDW boson with k-structure）定量检验。

## 数值/公式
- Ω_phonon = 100 meV
- U = 7t (strong coupling), t ~ 50 meV
- λ_m ∈ [0, 0.25]
- 动量网格: Nk = 4096
