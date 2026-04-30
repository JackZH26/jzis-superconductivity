# Magnetism and superconductivity in bilayer nickelate
- **作者:** Hui Yang, Ya-Hui Zhang
- **来源:** arXiv:2512.13793
- **年份:** 2025
- **研究线:** SC
- **精读日期:** 2026-04-10

## 核心贡献（一句话）
提出双层 type-II t-J 模型作为统一 SDW 磁序和超导的最小框架：小 J⊥ 给出 period-4 条纹 SDW（一致常压实验），大 J⊥ 稳定层间 s-wave 超导。

## 关键方法论
1. **Type-II t-J 模型**：从双 Kondo 模型在 J_H→∞ 极限推导，保留 5 维局域 Hilbert 空间（2个 spin-1/2 d⁷ + 3个 spin-1 d⁸ 态）
2. **iDMRG**：在 L_y=4, L_z=2 柱面上计算，bond dimension 达 m=10000
3. **关键对比**：type-II t-J vs 单轨道 t-J — 在小 J⊥ 时两者定性不同（单轨道有配对 gap，type-II 是 Luttinger liquid）

## 主要结果
1. **J⊥=0 极限**：双交换铁磁（J‖=0）或 period-4 SDW（J‖>0）— SDW 来自双交换 FM 与 Néel 序的竞争
2. **SDW→SC 相变**：J⊥,c ∈ (0.5, 1)t 处发生
3. **配对证据**：
   - 自旋 gap：J⊥≥0.3 时有限（Luther-Emery liquid）
   - Cooper pair 关联：J⊥≥1 时幂律衰减，指数 α<2（发散配对敏感度）
   - ξ_{2e}/ξ_e > 2 at J⊥≥1（Cooper pair 形成）
4. **单轨道模型过高估计配对**：大 J⊥ 时 spin gap 高 4-6 倍
5. **SDW 方向**：计算得 Q=(π/2, 0) 沿 x 方向，实验观测 Q=(π/2, π/2) 沿对角线 — 差异归因于 C4 破缺和有限 t_z

## 与我们研究的关联
- **★ d_{z²} 局域矩是磁序的关键**：这支持了我们的框架——d_{z²} 通过 Hund 耦合控制层间物理
- **J⊥ 是唯一调控参数**：从 SDW 到 SC 的相变完全由 J⊥ 驱动——与 Ji+2026 一致
- **单轨道 vs 双轨道**：type-II t-J 比单轨道 t-J 更真实地描述小 J⊥ 区间。这对我们理解常压 SDW 相很重要
- **相变点 J⊥,c**：SDW-SC 转变发生在 J⊥,c ∈ (0.5, 1)t，对应压力 ~14 GPa 的结构转变

## 潜在问题/局限
- L_y=4 柱面可能不足以准确定位 2D 中的 SDW-SC 相变
- 忽略了 d_{z²} 的层间 hopping t⊥^z（只保留 J⊥）
- x=0.5 掺杂下的大 J⊥ 给出绝缘体而非超导

## 关键数值
- SDW: Q = (π/2, 0), period-4
- SC 配对: 层间 s-wave
- 相变: J⊥,c ∈ (0.5, 1)t（L_y=4 at x=0.5）
- Spin gap: type-II t-J 约为单轨道的 1/4~1/6（更真实）

## 启发的新想法
1. **定量 J⊥,c → Pc 对应**：如果能将 J⊥,c ≈ 0.7t 对应到临界压力 Pc ≈ 14 GPa，就能给出 t-J 模型参数与实验压力的直接校准
2. **常压薄膜的 SDW 检测**：模型预测弱应变（小 J⊥）时应有 SDW。查找 La₃Ni₂O₇/STO 或 /LSAT 薄膜的中子/μSR 数据
