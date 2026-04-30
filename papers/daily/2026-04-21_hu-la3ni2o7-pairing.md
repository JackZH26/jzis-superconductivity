# Hu+2026: Pairing Mechanism in Bilayer Nickelate La₃Ni₂O₇ Superconductors

**arXiv:** 2604.17181  
**Authors:** Tao Xiang, Jiangping Hu  
**Date:** 2026-04-19

## 核心方法论
- Gene principle + collaborative Fermi-surface rule（之前统一 cuprate + iron-SC 的框架）
- 强耦合极限下推导 AFM superexchange
- 两个 dominant pairing channel 的合作效应分析

## 关键结果

### 两个主导 AFM 交换通道
1. **J⊥ — 层间 intra-orbital exchange**: dz² 轨道之间，通过内部顶端氧 (apical O) 介导
   - J⊥ = 4(t_zz^⊥)²/U
   - 产生 s-wave 层间 singlet pairing
   
2. **Jxz — 层内 inter-orbital exchange**: dz² 和 dx²-y² 之间，通过平面氧介导
   - Jxz = 2txz²/(U+Δxz) + 2txz²/(U-Δxz)
   - 具有非平凡动量结构（因 dx²-y² 的 B₁g 对称性）

### s± 超导态
- 两个通道**合作**而非竞争 → 产生 robust s± 态
- 符号反转: mirror-even pockets (α, γ) 与 mirror-odd pocket (β) 之间
- Gap 形式因子: (cos kx - cos ky)² 在 β pocket 上最大化
- 类比 iron pnictides 的 s± 但编码在 bilayer mirror quantum number 中

### Fermi surface 分类
- α pocket (Γ 中心): 层对称 L+, 轨道同相 O+ 
- β pocket (大 FS，类 cuprate): 层反对称 L-, 轨道反相 O-
- γ pocket (M 附近，小): 层对称 L+, 轨道反相 O-
- dz² bonding state 近半填充 → 强关联
- dx²-y² 仅约 1/4 填充 → cuprate 型 d-wave pairing 被抑制

### 为什么不是 d-wave
- dx²-y² 远离半填充 → NN Cu-O-Cu 型 superexchange 强烈抑制
- J⊥ 不贡献 d-wave pairing（层间 exchange 本身是 s-wave）
- d-wave 需要的 NN dx²-y²-O-dx²-y² exchange 太弱

## 与已有工作的区别
- 统一框架: 将 La₃Ni₂O₇ 纳入 gene principle + collaborative FS rule
- 之前缺乏共识 → 这里给出明确的 s± 预言
- 区别于纯 J⊥ 模型: 加入 Jxz 是关键

## 启发的新想法
**假设:** bilayer nickelate 的 J⊥ 由 apical O 介导 → 如果能增强 t_zz^⊥ (例如通过化学压力或应变)，可以提高 Tc
- 可验证: 对比不同 rare-earth 替换 (La vs Pr vs Nd) 的 t_zz^⊥ 和 Tc

## 与研究的关联
- Nickelate 提供了非 e-ph 超导的理论框架 → 对比我们的 hydride e-ph 路线
- s± vs d-wave 的判据可能启发 hydride 中的对称性分析
- Gene principle 的"准二维 + 强杂化"条件也可用于筛选 hydride 候选材料？

## 数值/公式
- J⊥ = 4(t_zz^⊥)²/U, 其中 t_zz^⊥ ≈ 0.5-0.6 eV (from DFT)
- Jxz = 2txz²/(U+Δxz) + 2txz²/(U-Δxz)
- Ni 平均价态 +2.5, eg 轨道分布 n=1.5 electrons/site
