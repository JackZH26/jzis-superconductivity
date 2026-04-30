# 精读笔记 — Spin Fluctuations in the Rare-Earth Doped Bilayer Nickelates

**arXiv:** 2601.14946
**作者:** Honglin Zhou, Xinman Ye, Gang Wang, ... Huiqian Luo
**年份:** 2026
**线:** SC

## 核心方法论
- INS (非弹性中子散射) 研究 Pr/Nd 掺杂的 La₃Ni₂O₇₋δ 粉末样品
- 在 ISIS MERLIN 和 ILL PANTHER 飞行时间谱仪上测量
- 用有效 Heisenberg 模型 (仅考虑最近邻交换耦合) 的 SpinW 计算拟合数据
- 基于 stripe-type 反铁磁序拟合参数

## 关键结果
1. **La₃Ni₂O₇₋δ 的 45 meV flat mode 在掺杂后分裂为两个模式 (43 meV + 48 meV)，并出现额外 60 meV 模式**
2. **层间耦合增强:** SJ⊥ 从 ~60 meV (纯 La) 增强到 ~69 meV (Pr) 和 ~73 meV (Nd)
3. **层内耦合极弱:** SJ∥ ≤ 3.5 meV，与铜氧化物 (J∥ 主导) 形成鲜明对比
4. Nd 掺杂样品的自旋涨落强度比 La 和 Pr 样品都强
5. CEF (晶体场) 激发: Nd 在 5.5 和 22 meV，Pr 在 2-6 meV 范围内
6. 稀土掺杂提供化学压力，修改层间耦合和 dz² 轨道电子结构

## 精确数值摘录
- SJ⊥(La) ≈ 60 meV, SJ⊥(Pr) ≈ 69 meV, SJ⊥(Nd) ≈ 73 meV [来源: 本文 INS 拟合]
- SJ∥ ≤ 3.5 meV [来源: 本文]
- La₃Ni₂O₇ AF 转变温度 TN ≈ 147 K [来源: 本文磁化率数据]
- μ_eff(Nd) = 2.8 μB, μ_eff(Pr) = 3.7 μB [来源: 本文 CW 拟合]
- Ni 磁矩 ≈ 0.22-0.85 μB [来源: μSR/中子衍射, 引用文献]
- Tc 从 80K → 接近 100K (稀土掺杂 La₃Ni₂O₇) [来源: 引用文献]

## 与已有工作的区别
- 首次在掺杂镍基超导体中观测到 45 meV 模式的分裂
- 这种分裂行为在铜氧化物和铁基中从未观测到
- 直接实验证据表明层间耦合是驱动 Tc 的关键参数

## 启发的新想法
**假设:** J⊥ 增强 ~20% (60→73 meV) 对应 Tc 增强 ~25% (80→100 K)。如果这个线性关系成立，需要 J⊥ ≈ 150 meV 才能达到 200 K，但这可能超出 Ni-O-Ni 180° 键角的极限。可以计算 J⊥ vs Tc 的定量关系并与 s± 配对模型预测对比。

## 与研究的关联
★★★ **直接验证我们的 J-维度 tradeoff 猜想中最关键的一环:** 层间耦合 J⊥ 是 nickelate 超导的主导参数。数据显示 J⊥ 增强 → Tc 升高，但 J⊥ 的上限受制于结构 (Ni-O-Ni 键角 → 180°)。这强化了 "J-维度 tradeoff" 的图景: nickelate 已经是 2D 系统中 J⊥ 占优的极端情况，但要 300K 仍然不够。
