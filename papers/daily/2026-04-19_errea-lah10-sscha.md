# Errea et al. — Quantum Crystal Structure in the 250K SC LaH₁₀
**arXiv: 1907.11916 | Nature 578, 66 (2020)**

## 核心结论
- LaH₁₀ 在 Fm-3m 结构下 λ_anh ≈ 3.5（SSCHA 计算）
- 经典计算预测 230 GPa 以下发生畸变，但量子零点运动稳定了 Fm-3m 结构
- SSCHA 将能量景观从多个局部最小值简化为单一 Fm-3m 基态
- 计算 Tc 与实验 250K 吻合

## 方法论
1. **SSCHA (Stochastic Self-Consistent Harmonic Approximation)**:
   - 将完整的非谐/相互作用晶格映射到辅助谐振系统
   - 通过蒙特卡洛采样最小化辅助谐振系统的自由能
   - 关键优势：同时处理量子离子效应 + 非谐性 + 温度
2. 超胞 DFT 计算 → SSCHA 力常数 → 非谐声子色散
3. 从非谐声子计算 α²F(ω) → λ → Tc

## 关键数值
- LaH₁₀ Fm-3m: λ_harm ≈ 2.6（谐振）→ λ_anh ≈ 3.5（SSCHA）
- ★ 这是我们 latest_state 中唯一一个 λ_anh > λ_harm 的例子
- 原因：Fm-3m 是谐振不稳定的（虚频模），SSCHA 通过量子涨落稳定后，软模贡献大量 e-ph 耦合
- 137-218 GPa 范围内 Tc 弱依赖压力

## 启发的新想法
1. **★★★ 谐振不稳定是 λ_anh 增强的关键标志** — 验证了我们 Night 34 的设计原则 #10
2. **假设可验证**: 任何在 DFPT(harmonic) 下有虚频但被 SSCHA 稳定的氢化物，都应有 λ_anh > λ_harm
3. LaH₁₀ 的 ω_log 是多少？文中没直接给出 — 需要从 α²F(ω) 反算

## 与研究的关联
- 直接验证了我们 Night 34 设计规则 #5: λ_anh > λ_harm only for harmonically unstable
- 为 300K 设计提供明确路径: 找 LaH₁₀ 型的谐振不稳定 + 更高 ω_log 的材料
- 需要计算: LaH₁₀ 的 ω_log → 验证 λ_anh · ω_log ≈ 3413K (latest_state 数值)

## 精确数值
- λ_anh ≈ 3.5 [Errea+2020, Nature 578, 66]
- Tc_exp = 250K @ 170 GPa
- 稳定压力范围: 137-218 GPa
