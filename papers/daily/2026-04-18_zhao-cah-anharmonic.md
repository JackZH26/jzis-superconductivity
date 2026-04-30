# Zhao+2025/26: Revisiting Phase Stability and Superconductivity in Ca-H with Anharmonic Effects

**arxiv:** 2512.03721 | **Authors:** Zhao, Wang, Sun, Li, Liu, Xie (Jilin Univ.)

## 核心方法论

SSCHA + ACNN（机器学习势）大规模计算 Ca-H 体系的温度-压力相图：
1. ML 加速结构搜索 Ca₈Hx (32≤x≤48) @ 130 GPa
2. 0K harmonic 相图 → Ca₈H₄₄-Ca₈H₄₆ 在凸包上
3. 加入 anharmonic 修正后重建完整 T-P 相图
4. 对稳定相计算超导 Tc

## 关键结果

### 相稳定性（颠覆认知！）
- **CaH₆ 在 0K 并非基态！** 即使加 ZPE 仍在凸包上方 7-9 meV/atom
- Ca₈H₄₆（type-I clathrate）才是 0K 基态（130-200 GPa）
- **CaH₆ 在 ~500K 才热力学稳定**（anharmonic 结果，harmonic 给 >1900K）
- Anharmonic 效应：high-freq modes soften, low-freq modes harden

### 超导
- μ* = 0.10（默认）；也给了 μ*=0.13, 0.15 的值
- Tc 排序: CaH₆ > Ca₈H₄₆ > Ca₈H₄₅ > Ca₈H₄₄
- CaH₆ Tc 最高，与实验 ~215K 一致
- Ca₈H₄₆ Tc 比 CaH₆ 低约 30K（anharmonic level）
- 减压时 Tc 下降 = 氢含量减少（Ca₈H₄₆₋δ）

### LaSc₂H₂₄ 提及
文中提到 LaSc₂H₂₄ 已作为"第一个室温超导体"成功合成。[Song+2025]

## 与已有工作的区别
- 首次用 SSCHA-ACNN 完整重建 Ca-H anharmonic 相图
- 之前的研究（2024 年两篇 Ca₈H₄₆ 论文）仅用 harmonic 近似
- 首次发现 CaH₆ 是高温亚稳态，不是基态

## 启发的新想法
**Ca₈H₄₆ clathrate 可能比 CaH₆ 更容易在低温合成。** 如果我们的降压策略 focusing on ternary mixing (La,Ce) 系统，也需要考虑 clathrate 结构（如 H₁₈, H₂₉, H₃₂ cage）作为替代目标。

## 与研究的关联
- 验证了 CaH₆ 的 μ* = 0.10（我们用 0.13 可能偏高）
- Ca₈H₄₆ Tc 比 CaH₆ 低 30K → 实验中降压看到的 Tc 下降不是 CaH₆ 的本征行为，是相变到 Ca₈H₄₆₋δ
- ★ 提到 **LaSc₂H₂₄ 室温超导已实现** — 需要追踪此论文！

## 数值/公式
- CaH₆: Ehull = 7-9 meV/atom (anharmonic, 0K)
- CaH₆ stability onset: ~500 K (anharmonic)
- Ca₈H₄₆: dynamically stable down to 130 GPa (anharmonic)
- μ* = 0.10 (default), also 0.13, 0.15 in Table S8
