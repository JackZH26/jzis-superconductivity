# 精读笔记 — 3d_{z²} orbital delocalization in (La,Pr)₃Ni₂O₇₋δ films
**arXiv:** 2604.21899 | **作者:** Chen, Zhang, Peng, ... Zhou (Diamond + SUSTech + USTC) | **年份:** 2026

## 核心方法论
XAS (O K-edge, Ni L₃-edge) + RIXS，独立调控应变(LAO vs SLAO基底, -1% vs -2%)和氧含量(非SC vs SC样品)两个变量，追踪从非超导到超导相的微观演化。

## 关键结果
1. **两步演化**：
   - Step 1: 3d_{z²} 离域化 — O K-XAS 中谱重从上 Hubbard 峰 B 转移到空穴峰 A（仅在 π-极化/out-of-plane 方向观测到）
   - Step 2: SDW 序抑制 — RIXS 中长程 SDW 序的强度和关联长度均被抑制
2. **轨道选择性**：只有 O 2p_z 和 Ni 3d_{z²}（层间轨道）被影响，面内轨道(O 2p_{x,y}, Ni 3d_{x²-y²})几乎不变
3. **短程磁子存活**：虽然长程 SDW 被抑制，短程磁子仍然存在，带宽不变但变得阻尼
4. **两种调控殊途同归**：应变和氧含量调控产生完全相同的演化趋势

## 数值/公式
- SC LPNO/SLAO3: Tc ≈ 50 K
- 应变: LAO (-1%), SLAO (-2%)
- O K-XAS 峰 A 位于约 528 eV（空穴态），峰 B 约 529 eV（UHB）

## 启发的新想法
**假设**：层间 3d_{z²}-2p_z-3d_{z²} 分子轨道的离域化程度可以作为 nickelate 超导的"序参量"。可量化为 O K-XAS 中峰 A/峰 B 的谱重比 R = I_A/(I_A + I_B)。当 R 超过临界值 R_c 时超导出现。

## 与研究的关联
这是直接的实验证据，说明 nickelate 超导的关键通道是 z 方向层间耦合。这与我们 Two-Channel AD 框架中的"层间通道"概念高度一致：层间通道必须活跃才能产生高 Tc。
