# Beyond Homes scaling: disorder, the Planckian bound and a new universality
- **作者:** D. M. Broun, Vivek Mishra, J. S. Dodge, P. J. Hirschfeld
- **来源:** arXiv:2502.13351, Phys. Rev. X 15, 041005 (2025)
- **年份:** 2025
- **研究线:** SC
- **精读日期:** 2026-04-12

## 核心贡献（一句话）
证明 d 波超导体在 dirty limit 中 ρ_s0 ∝ (σ_dc·T_c)² 违反 Homes 标度，并通过 Drude 等离子体权重归一化揭示了新的普适标度——超流分数在 Planckian 散射极限处收敛到单一点。

## 关键方法论
- **Dirty BCS 形式主义：** 用 Nambu-Green 函数系统计算弹性散射对 s 波和 d 波超导的不同效应
  - s 波 dirty limit: ρ_s0 ∝ σ_dc·T_c（经典 Homes 标度）
  - d 波 dirty limit: ρ_s0 ∝ (σ_dc·T_c)²（新结果！平方关系！）
- **d 波的物理原因：** 非磁性杂质破坏 d 波对（Anderson 定理对 d 波不成立），导致超流密度额外抑制
- **非弹性散射（Migdal-Eliashberg）：** 引入强耦合玻色子谱（特征频率 Ω_B），当 Ω_B ~ 几倍 T_c0 时，得到 Planckian 散射率 ℏΓ ~ k_B·T_c
- **归一化方案：** 将 Homes 图的两轴都除以 Drude 等离子体权重 ω²_p,D，得到超流分数 f_s = ρ_s0/ω²_p,D vs k_B·T_c/(ℏΓ_tr)
- **四种标度区域：** Planckian（最优铜氧化物）、超洁净（Sr₂RuO₄）、dirty s-wave、dirty d-wave

## 主要结果
1. **[定理] d 波 dirty limit 标度：** ρ_s0 ∝ (σ_dc·T_c)² — 与 s 波的线性标度根本不同
2. **[定理] Planckian 收敛：** 归一化后，s 波和 d 波在 Planckian 散射极限处收敛到同一点（f_s ~ 1, k_B·T_c/ℏΓ ~ 1）
3. **[实验验证] 材料分类：**
   - Planckian 区: 最优掺杂铜氧化物、CeCoIn₅
   - dirty d-wave: 过掺 LSCO、欠掺 YBCO₆.₃₃₃
   - dirty s-wave: 传统超导体
   - 超洁净: Sr₂RuO₄
4. **[推论] 非弹性散射是铜氧化物 Homes 标度的真正原因** — 不是 disorder，而是 Planckian 散射

## 与我们研究的关联
- **直接改进三瓶颈框架 (B3 Homes 定律)：** Broun 等人的结果表明 Homes 标度的"普适性"实际上隐藏了 s/d 波的深刻差异。我们的 B3 瓶颈需要区分对称性
- **Planckian 散射是关键连接：** Harrison (2504.02179) 说 Homes 定律 ← Planckian 放松，Broun 这篇更深入地证明了这一点并给出了偏离的条件
- **对 nickelate 的预测：** 如果 nickelate 是 d 波超导体（Wang+2026 VMC 支持 d_x²-y²），那么它在 dirty limit 应该偏离 Homes 标度。这可以作为实验检验
- **超流分数 f_s 作为新诊断工具：** 我们可以用 f_s 来分类 nickelate 的散射机制是弹性还是非弹性主导

## 潜在问题/局限
- Migdal-Eliashberg 处理仍然是近似的（基于 Fermi 液体）
- 对欠掺铜氧化物的描述"surprisingly well"但不完美
- 需要 Drude 权重 ω²_p,D 的精确实验值，这对一些材料不易获得

## 关键数值（from paper）
- d 波 dirty limit: ρ_s0 ∝ (σ_dc·T_c)² [理论推导]
- Planckian 收敛点: f_s ~ 1, k_BT_c/ℏΓ_tr ~ 1 [Fig. 3]
- 强耦合参数: Ω_B = 3.5 T_c0 for cuprates [model]
- Published in Phys. Rev. X

## 启发的新想法
1. **[可验证] Nickelate Homes 标度测试：** 如果 LNO 薄膜的 σ_dc、T_c、λ_ab 数据可用，可以检查它落在归一化图的哪个区域。Phase-limited + d-wave 预测它应该在 dirty d-wave 区域。
2. **[假设] Planckian 散射与相刚度的关联：** Planckian 散射率 ℏΓ = α·k_BT（α~1）意味着散射时间尺度 ~ ℏ/k_BT。对于 T_c ~ 300K，这给出 τ ~ 25 fs。这与 Cooper 对的相位相干时间有什么关系？
3. **[关键约束] 3D 超导体避免 dirty d-wave 问题：** 氢化物在高压下是 3D+s 波，自然落在 Homes 标度线上。这解释了为什么 3D 结构对高 T_c 有优势——不受 d 波 disorder 惩罚。
