# Search for thermodynamically stable ambient-pressure superconducting hydrides in GNoME database

**arXiv:** 2508.19781v3 | **作者:** Sanna, Cerqueira, Cubuk, Errea, Fang
**发表:** Commun Phys 9, 94 (2026) | **日期:** 2025-08-27

## 核心方法论

从 GNoME 材料数据库（38.1 万种 0K 稳定晶体）中筛选立方氢化物超导体。

**多阶段流程：**
1. 数据挖掘：490 个立方金属氢化物 (GNoME)
2. DFT 自旋极化计算 → 261 个非磁性金属
3. ALIGNN 机器学习模型预测 Tc → 筛选 Tc_pred ≥ 1K
4. 高通量 DFPT + Allen-Dynes 公式 → 最终验证

## 关键结果

- 找到 **25 个立方氢化物** Tc > 4.2K（液氦沸点）
- 最高 Tc = **17K** (LiZrH₆Ru，vacancy-ordered double perovskite)
- 精确计算：λ = 1.20, ω_log = 343.32 K → Tc^AD ≈ 23.5K (高通量)，Tc ≈ 17K (精细)
- ALIGNN vs DFPT MAE = 2.5K（机器学习预测精度高）
- **两大结构族：** vacancy-ordered double perovskites + fluorite-like

**核心发现：高 Tc (~100K) 似乎系统性地与热力学不稳定性挂钩**
- 热力学稳定的氢化物 Tc 上限 ~17K
- 高 Tc 预测（RbPH₃ ~100K）都是亚稳态

## 与研究的关联

**SC 方向关键启发：**
- 我们追求的 300K 候选材料（如 LaSc₂H₂₄）大概率是热力学不稳定的
- 这意味着 PQP（压力淬火）方法变得更重要——合成亚稳态材料的可行路径
- ALIGNN 模型可以作为我们 AD/Eliashberg 工作的补充工具

## 启发的新想法

**假设：** 存在一个 Tc vs 热力学稳定性的 tradeoff。可以用 GNoME + 凸包距离 (E_above_hull) 作为横轴，Tc 作为纵轴，绘制"稳定性-Tc 相图"。这个关系的数学形式（如果存在）可以指导材料设计策略。

## 数值/公式

- LiZrH₆Ru: λ = 1.20 [VERIFIED, 2508.19781], ω_log = 343.32 K, Tc^AD ≈ 23.5K
- EuCdH₆Ru: λ = 2.53, ω_log = 84.40 K, Tc ≈ 13.6 K [同上]
- ALIGNN MAE = 2.5 K
- 热力学稳定 + 常压 + 立方 → Tc 上限 ~17K
