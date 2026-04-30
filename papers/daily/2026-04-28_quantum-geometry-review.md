# Quantum geometry in superfluidity and superconductivity

**arXiv:** 2308.08248v2 | **作者:** Peotta, Huhtinen, Törmä (Aalto)
**发表:** Proc. Enrico Fermi School 211 (2025) | **综述论文**

## 核心方法论

系统综述了量子几何（quantum metric, Berry curvature）在多带系统超流/超导中的作用，特别是平带超导。

**关键框架：**
- 量子几何张量 (QGT) B_ij = 2 Tr[P ∂_ki P ∂_kj P]
- 实部 = 量子度规 g_ij (Bures distance)
- 虚部 = Berry 曲率 (Chern number)
- 超流密度 Ds = 常规项（反比于有效质量）+ **几何贡献**（由量子度规决定）

## 关键结果

1. **平带中超流密度完全由量子几何决定**
   - 常规 BCS: Ds ∝ 1/m* → 平带 m* = ∞ → Ds = 0
   - 但几何贡献 Ds^geom 在平带中可以非零！
   - 非零条件 = 带的量子几何/拓扑非平凡
   
2. **Tc ∝ |U| 在平带中**（线性而非 BCS 的指数压制）
   - 但需要 Ds ≠ 0 才有真正超导（否则 Cooper 对局域化）
   
3. **拓扑下界定理：** 平带超导的超流密度有一个由最小量子度规决定的下界
   - Ds ≥ (minimal quantum metric bound)

4. **Wannier 函数重叠的物理解释：** 平带超流电流 = 相邻 Wannier 函数间的重叠

5. **自洽序参量对超电流的依赖** 被正确处理（之前工作的缺陷）

## 与研究的关联

**SC 方向转型：**
- 如果我们转向非 BCS 机制，量子几何超导是一个理论严谨的方向
- moiré 系统（twisted graphene）中已有实验验证
- 关键问题：能否在氢化物类材料中找到具有大量子度规的平带？

## 启发的新想法

**假设：** 在 H₂₄ cage 结构中，如果存在因 cage 几何导致的近平带，其量子度规可能提供额外的超导增强机制（beyond Eliashberg）。可用 DFT 能带计算验证是否存在近平带。

## 数值/公式

- QGT: B_ij(k) = 2 Tr[P(k) ∂_ki P(k) ∂_kj P(k)]
- 超流密度: Ds = Ds^conv + Ds^geom
- 平带 Tc ~ |U| (线性) vs BCS: Tc ~ exp(-1/(ρ(EF)|U|))
- Chern number C = (1/2π) ∫_BZ d²k Im B₁₂(k)
