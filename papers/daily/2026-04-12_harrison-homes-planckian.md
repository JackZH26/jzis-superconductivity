# Homes' Law and Universal Planckian Relaxation
- **作者:** M. K. Chan, R. D. McDonald, N. Harrison
- **来源:** arXiv:2504.02179
- **年份:** 2025
- **研究线:** SC
- **精读日期:** 2026-04-12

## 核心贡献（一句话）
证明 Homes 定律是 strange metal 线性电阻率（ρ=AT）的直接推论，Planckian 无量纲系数 α ≈ 2.6 由实验确定，定律的宽适用范围来自有效质量的大幅变化而非散射率变化。

## 关键方法论
- **从 Homes 定律推导 Planckian 散射：** 
  - 左边: λ_L⁻² = 4πe²(n/m*)/c²（BCS 穿透深度）
  - 右边: σ(T_c)·T_c，用 Drude 公式 σ = e²(n/m*)τ
  - 代入 Planckian: ℏ/τ = αk_BT_c
  - 得到 C = α × (k_B/ℏ)/πc² ≈ α × 42 Ωcm⁻¹K⁻¹
  - 实验拟合: α ≈ 2.6（与独立比热、光学测量一致）
- **三个关键推论：**
  1. 正常态在 T_c 附近的电阻率是 T-线性的
  2. Planckian 无量纲系数 α ~ O(1)
  3. 适用范围来自 n/m* 的多数量级变化（不是散射率变化）
- **Zaanen 的解释澄清：** Zaanen (2004) 说铜氧化物 T_c 高是因为"metallic state is as viscous as quantum mechanics permits"。Harrison 澄清：Planckian 散射不设 T_c 上限，真正设 T_c 尺度的是等离子体频率

## 主要结果
1. **[定理] Homes 定律 = 线性电阻率 + Planckian 散射** — 简洁推导
2. **[实验] α ≈ 2.6** — 从 Homes 图的斜率确定
3. **[洞察] n/m* 是 spread 的来源：** 铜氧化物中 n/m* 随掺杂变化一个数量级
4. **[洞察] Homes 定律不设 T_c 上限：** 与 Zaanen 的原始解释不同
5. **[洞察] 质量增强机制与 Planckian 散射独立：** Homes 定律成立的条件

## 与我们研究的关联
- **三瓶颈框架的 B3 瓶颈精确化：** Homes 定律的真正含义是 ℏ/τ ≈ α·k_BT_c。对于 T_c = 300K，τ ~ ℏ/(αk_B·300) ~ 10 fs。这是散射时间的 Planckian 极限。
- **等离子体频率决定 T_c 尺度：** ω²_p = 4πe²n/m*。增大 n 或减小 m* 都能提高 T_c 的"天花板"
- **与 Broun 的互补：** Harrison 给出大图景（Homes = Planckian），Broun 给出细节（dirty d-wave 偏离）
- **对室温超导的约束：** 如果 Homes 定律不设 T_c 上限，那么限制来自 ω_p（等离子体频率）。这意味着高载流子密度 + 轻有效质量是核心要求

## 潜在问题/局限
- 仅 3 页，推导简洁但缺少微观机制
- α ≈ 2.6 大于通常引用的 α ~ 1，需要解释差异（可能是定义差异）
- 对 cuprate 相图中偏离 strange metal 区域的处理较粗糙（"logarithmic accuracy"）
- 不解释为什么 α 在不同材料中近似相同

## 关键数值
- α ≈ 2.6 [从 Homes 图斜率]
- C ≈ α × 42 Ω cm⁻¹ K⁻¹ [计算]
- n/m* 在铜氧化物中变化 ~10× [来自 Legros+2019, Shekhter+2024]

## 启发的新想法
1. **[可验证] 用 α = 2.6 反推 nickelate 的预期 Homes 位置：** 如果 nickelate 遵循 Homes 定律，给定 T_c(p) 和 σ_dc(T_c)，可以预测 λ_L。与实验比较可以判断 nickelate 是否是 Planckian strange metal。
2. **[假设] Planckian 散射与量子纠缠：** Harrison 引用了 Zaanen 的"many-body entanglement"解释和夸克-胶子等离子体类比。这暗示 Planckian 散射可能是量子混沌的标志——与 SYK 模型的联系值得探索。
3. **[关键约束] 室温超导的 ω_p 要求：** 对 T_c = 300K，用 Homes 定律反推：需要 σ_dc(300K)·300 ≈ ρ_s0。如果 σ_dc ~ 10⁴ Ω⁻¹cm⁻¹（典型金属），则 ρ_s0 ~ 3×10⁶ Ω⁻¹cm⁻¹K，对应 λ_L ~ 150 nm——与铜氧化物相当！所以 Planckian 散射不排斥 300K，但需要同等级的等离子体频率。
