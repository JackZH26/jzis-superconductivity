# 精读笔记 — 3D Fermi Surface, Van Hove Singularity and Enhancement of SC in Infinite-Layer Nickelates

**arXiv:** 2504.18778
**作者:** Chengliang Xia, Shengjie Zhou, Hanghui Chen
**年份:** 2025
**线:** SC

## 核心方法论
- **RPA+DMFT 组合方法** 求解线性化 gap 方程
- 比较 infinite-layer nickelate 的 3D 费米面 vs 假想的 2D 类铜氧化物费米面
- 聚焦 kz 色散和 Van Hove singularity (VHS) 的作用
- 关键: infinite-layer nickelate 有明确的 kz 色散，区别于铜氧化物

## 关键结果
1. **3D 费米面上的 VHS 增强自旋涨落** — 驱动系统更接近 AFM 不稳定性
2. **相比 2D 费米面，3D VHS 显著增强超导配对**
3. kz 色散不是削弱超导 (如我们的 J-维度 tradeoff 假设)，而是通过 VHS 增强
4. 精细的费米面特征 (VHS 位置) 对材料特定的超导性质至关重要
5. 适用于 infinite-layer (NdNiO₂ 类)，而非 bilayer (La₃Ni₂O₇ 类)

## 精确数值摘录
- 具体增强因子需查正文 (仅获取摘要)
- 系统: infinite-layer nickelate (与 La₃Ni₂O₇ 不同)

## 与已有工作的区别
- 之前的 nickelate 研究主要聚焦 2D 费米面或 bilayer 结构
- 本文首次系统比较 3D vs 2D 费米面对超导的影响
- 发现 VHS 是关键机制，不仅仅是 3D 带宽效应

## 启发的新想法
**★ 关键假设:** 我们的 J-维度 tradeoff 可能过于简化。3D 化不一定稀释 J — 如果 3D 化同时引入 VHS (费米能级附近的 DOS 奇点)，可以通过增强 nesting 来增强自旋涨落。**修正版 tradeoff:**
- 2D → 强 J 但相位涨落限制 Tc
- 3D (无 VHS) → J 被稀释 → 低 Tc
- **3D (有 VHS) → J 不被稀释 + VHS 增强 pairing → 可能突破?**

这意味着 300K 路径不是简单的 "最大化 J" 或 "最大化 3D"，而是 "找到有 VHS 的 3D 结构"。

## 与研究的关联
★★★ **直接修正我们的 J-维度 tradeoff 框架:**
1. 3D 不等于 J 稀释 — 如果费米面拓扑正确 (有 VHS)，3D 反而增强
2. **新设计规则:** 寻找 3D 材料时，不仅看 J，还要看费米面是否有 VHS at EF
3. 这为 "高压 3D nickelate" 方向提供了具体的理论指导: 检查高压下费米面重构是否引入新 VHS
