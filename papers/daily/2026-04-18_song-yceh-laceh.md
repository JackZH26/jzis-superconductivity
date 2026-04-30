# Song+2022: Potential high-Tc in YCeHx and LaCeHx under pressure

**arxiv:** 2204.01921 | **DOI:** 10.1016/j.mtphys.2022.100873 | **Published:** Matter and Radiation at Extremes (2022)
**Authors:** Song, Hou, Nakano, Hongo, Maezono

## 核心方法论

进化算法（CALYPSO）结构预测 + DFT 电子-声子耦合：
1. 对 Y-Ce-H 和 La-Ce-H 体系进行全局结构搜索（100-300 GPa）
2. 检查热力学和动力学稳定性
3. 用 Allen-Dynes 修正 McMillan 公式计算 Tc
4. 高温分解阈值评估

## 关键结果

### 稳定相
- **P-6m2 YCeH₁₈**: H₁₈ cage, stable at 150 GPa
- R-3m YCeH₂₀: H₃₂ cage, stable at 300 GPa
- P4/mmm YCeH₈, LaCeH₈: lower H content
- R-3m LaCeH₂₀: H₃₂ cage, stable at 250 GPa
- 所有 clathrate 结构在高温下也有良好热稳定性

### 超导（AD McMillan 公式）
| 相 | 压力 | Tc | λ | ω_log |
|-----|------|-----|-----|-------|
| YCeH₁₈ (P-6m2) | 150 GPa | **173 K** | — | — |
| YCeH₂₀ (R-3m) | 300 GPa | 122 K | — | — |
| LaCeH₂₀ (R-3m) | 250 GPa | 116 K | — | — |

**注：** 具体 λ 和 ω_log 值需查原文表格 [UNVERIFIED: need original paper]

### Ce 的关键角色
- Ce 在高压下 4f 电子行为变化（4f¹ → 4f⁰ transition）
- Ce 的化学预压缩效应 → 降低稳定化所需外压
- 与 (La,Y)H₁₀ 类似的合金策略

## 与已有工作的区别
- 首次系统研究 Y-Ce-H 和 La-Ce-H 三元体系
- 之前 (La,Y)H₁₀ 达到 253K（Semenok+2021），但需 ~180 GPa
- YCeH₁₈ 在 150 GPa 实现 173K → Tc/P = 1.15 K/GPa

## 启发的新想法
**YCeH₁₈ 是 clathrate 路径的代表。** 虽然 Tc = 173K 低于 LaH₁₀ (250K)，但压力低得多（150 vs 170 GPa）。三元混合的降压效果明显。对我们的 "300K 设计窗口"：需要比 YCeH₁₈ 更强的耦合或更高 ω_log。

## 与研究的关联
- 直接回答 latest_state 问题 "Why does Ce enable >200K at 100 GPa?"
  - Ce 不能在 100 GPa 实现 200K（本文最高 173K@150GPa）
  - latest_state 中的 "(La,Ce)H₉₋₁₀" 数据来自 Bi+2022 和 Chen+2024，不是本文
- Tc/P = 1.15 K/GPa vs 我们记录的 2.0 → 本文结果偏保守

## 数值/公式
- YCeH₁₈: Tc = 173 K @ 150 GPa, P-6m2 structure
- YCeH₂₀: Tc = 122 K @ 300 GPa, R-3m structure
- LaCeH₂₀: Tc = 116 K @ 250 GPa, R-3m structure
- Allen-Dynes modified McMillan formula used
