# Mishra+2025: Electron-phonon vertex correction effect in superconducting H₃S

**arxiv:** 2507.01897 | **DOI:** 10.1038/s41524-025-01818-9 | **Published:** npj Comp. Mat. 11, 342 (2025)
**Authors:** Mishra, Mori, Margine (Binghamton Univ.)

## 核心方法论

在 Eliashberg 形式主义内加入一阶 e-ph vertex corrections：
1. Nambu 形式 → electron self-energy with vertex-corrected diagrams
2. 需要计算 **四个不同的 e-ph 矩阵元**（两个声子）
3. Full-bandwidth (FBW) + Fermi-surface restricted (FSR) 两种方案
4. 在 EPW 代码中实现
5. 同时考虑 anharmonic phonons (SSCHA)

**关键物理：**
- Migdal 定理要求 λ(ℏω₀/εF) ≪ 1
- H₃S at 200 GPa: ℏω₀/εF ≈ **5** → Migdal 严重失效！
- 原因：Fermi 面附近的 van Hove singularity → εF 很小

## 关键结果

### H₃S (Im-3m, 200 GPa)
- Standard ME (harmonic): Tc 过高（~250K vs 实验 203K）
- Vertex correction coupling λ^V 是 adiabatic λ 的显著比例
- **Vertex + anharmonic + DOS energy dependence → Tc ≈ 实验值**
- 三个效应缺一不可：
  - Anharmonic: phonon hardening → λ 降低
  - Vertex: 进一步修正 e-ph 耦合
  - DOS 能量依赖: vHs 的精确处理

### Pb
- 绝热近似完全成立
- Vertex corrections 可忽略（<1% 变化）
- Standard ME 给出正确 Tc

## 与已有工作的区别
- **首次从第一性原理完整计算 H₃S 的 vertex corrections**
- 之前要么用模型 Hamiltonian，要么用各向同性近似 + 因式分解近似
- 证明对高 Tc hydrides，三个效应（anharmonic + vertex + DOS）同时重要

## 启发的新想法
**★ Modified Allen-Dynes 公式对 H₃S 可能本质上不够用。** AD 假设绝热极限，但 H₃S 的 ℏω₀/εF ≈ 5 远超绝热范围。我们用 AD 得到的 Tc 预测需要加上 non-adiabatic 修正。对 λ>2 的强耦合体系，full Eliashberg 是最低标准，vertex corrections 可能需要。

## 与研究的关联
- 解释了为什么我们 Night 33 的 AD 预测对 H₃S 吻合较好（205K vs 204K）— 可能是 over-counting: AD 的 f₁f₂ 修正 + 固定 μ*=0.13 恰好抵消了 non-adiabatic 效应
- 对 LaH₁₀（λ=3.5）：vertex corrections 可能同样重要
- **300K 设计窗口需要考虑 non-adiabatic 上限**

## 数值/公式
- H₃S at 200 GPa: ℏω₀/εF ≈ 5
- Migdal parameter λ(ℏω₀/εF) >> 1 for H₃S
- λ^V / λ ≈ significant fraction (need exact number from full text)
- Final Tc (vertex + anharmonic + DOS) ≈ experimental ~200K
