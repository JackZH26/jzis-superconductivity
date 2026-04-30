# Lu+2026: Inverse Isotope Effect in SrPdH/D₂.₉

**arxiv:** 2602.23691 | **Authors:** Lu, Sahoo, Lucrezi, Hutcheon, Sinha, Ferreira, Pickard, Heil, Strobel (Carnegie + Graz)

## 核心方法论

Theory-guided discovery + experimental verification:
1. 高通量计算筛选 Sr-Pd-H 三元体系
2. 找到 SrPdH₃ 在常压下热力学稳定
3. 合成：560 bar, 475°C → SrPdH₃₋ₓ
4. 中子衍射确认组成：SrPdD₂.₉₍₂₎（96% D site occupancy）
5. DFPT + Wannier (EPW) + SSCHA 计算 e-ph coupling

## 关键结果

### 实验
- **Tc = 2.1 K (H), 2.2 K (D)** — 反同位素效应！
- 通常 BCS: Tc ∝ M^{-α}, α>0 → deuteride 应该 Tc 更低
- 上临界场: μ₀Hc2(0) = 0.31 T (D)
- AC 磁化率确认超导

### 理论
- DFPT 预测 Tc ≈ 2.8 K
- 反同位素效应来自 **量子零点运动**：
  - D 比 H 重 → 零点振幅更小 → 晶格更"经典"
  - 但对 SrPdH₃，零点运动 **增强** 了某些声子频率 → 改变 α²F(ω)
  - 净效果：H 的 λ 比 D 低（零点运动引起的 phonon hardening 超过 mass effect）

### 钙钛矿氢化物展望
文中列出大量理论预测的高 Tc 钙钛矿氢化物（常压/低压）：
- SrAuH₃: 132 K
- KInH₃: 73 K
- SrZnH₃: 107 K
- KGaH₃: 146 K (10 GPa)
- CsTlH₃: 163 K (10 GPa)
- RbTlH₃: 170 K (10 GPa)

## 与已有工作的区别
- **首次在钙钛矿氢化物结构原型中实验证实超导**
- 首次定量重现三元氢化物中的反同位素效应
- 之前 Bronger 1994 合成过 SrPdH₂.₇ 但未测量超导

## 启发的新想法
**★ 钙钛矿氢化物是 300K 的替代路径！** 虽然 SrPdH₃ 只有 2K，但理论预测 SrAuH₃ = 132K, CsTlH₃ = 163K 在 10 GPa。如果这些预测可靠，钙钛矿氢化物可能比 clathrate hydrides 更容易实现低压高 Tc。需要重点追踪 Du+2024 的 5 个 >120K 钙钛矿预测。

## 与研究的关联
- 零点运动导致反同位素效应 → 我们的 AD 公式完全忽略了这个
- 钙钛矿框架 = 新的材料设计空间（不需要 >100 GPa）
- **LaSc₂H₂₄ 室温超导** 在 Zhao+2026 和 Lu+2026 中都被引用 → 必须追踪

## 数值/公式
- SrPdH₃: a = 3.839(3) Å (expt), 3.848 Å (theory, 0.23% error)
- Tc(H) = 2.1 K, Tc(D) = 2.2 K
- Tc(theory, DFPT) ≈ 2.8 K
- Synthesis: 560 bar, 475°C
- μ₀Hc2(0) = 0.31 T (D sample)
