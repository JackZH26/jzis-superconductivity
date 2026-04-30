# 精读笔记 — Two-gap→Single-gap in Intercalated Bilayer PdTe₂
**arXiv:** 2604.21635 | **作者:** Han, Qiao, Jiang, Zhang, Wang, Zhang, Ting, Lu | **年份:** 2026

## 核心方法论
第一性原理 + Wannier 插值 + 全各向异性 Migdal-Eliashberg (ME) 方程。系统研究碱金属(Li/Na/K/Rb/Cs)插层双层 PdTe₂。

## 关键结果
1. **Tc 增强**：从 pristine 的 1.4 K 增至 5.0-13.5 K，Rb 插层最高 13.5 K
2. **Two-dome Tc 演化**：随插层原子增大，Tc 先升后降再升
3. **Two-gap→Single-gap 转变**：Li 插层保持双间隙；Na/K/Rb/Cs 转为单间隙。机制：插层扩大层间距 → 削弱层间耦合 → 消除 FS 各向异性
4. **拓扑共存**：pristine + Li/Na 插层保持非平庸拓扑（Z₂ 不变量）
5. **应变调控**：双轴拉伸可进一步增至 14.5 K

## 数值/公式
- Pristine Pd₂Te₄: λ = 0.50, ω_log = 119.1 K, Tc ≈ 1.4 K (MAD)
- RbPd₂Te₄: Tc = 13.5 K (anisotropic ME)
- 层间距从 2.52 Å (pristine) 到 ~4-5 Å (大碱金属)
- Te 面内振动主导 EPC

## 与已有工作的区别
首次对 PdTe₂ 系统进行全各向异性 ME 求解，揭示了双间隙→单间隙转变的微观机制。

## 启发的新想法
**假设**：层间耦合强度与超导间隙数的关系可能是一个更一般的原理。可以定义临界层间距 d_c，当 d > d_c 时双间隙消失。对于氢化物中的层状结构，类似的层间 e-ph 耦合调控可能影响 Tc。

## 与研究的关联
直接相关：
- 全各向异性 ME 方程的具体实现 → 验证我们 AD→Eliashberg 校正因子
- ω_log = 119.1 K 的具体数据可用于基准测试
- Two-dome Tc 行为可能对应 ω̄₂/ω_log 的非单调变化
