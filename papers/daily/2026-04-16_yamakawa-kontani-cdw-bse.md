# 精读笔记 — Theory of superconductivity and mass enhancement near CDW critical point (BSE method)

**arXiv:** 2508.19536
**作者:** Youichi Yamakawa, Hiroshi Kontani
**年份:** 2025
**线:** SC

## 核心方法论
- **Bethe-Salpeter 方程 (BSE)** 评估 2D Hubbard 模型中的电子-电子相互作用
- 满足 Baym-Kadanoff 守恒近似的标准
- 关键创新: 包含 **Aslamazov-Larkin (AL) 顶角修正** — 描述自旋涨落之间的干涉过程
- AL 顶角修正在 charge channel 产生 **吸引相互作用**
- 应用于方格子 Hubbard 模型 (铜氧化物)

## 关键结果
1. **电荷涨落的吸引作用 + 自旋涨落的排斥作用 → 协同产生高 Tc d-wave 超导**
2. 仅靠自旋涨落 (RPA 级别) 不够 — 需要电荷通道的额外贡献
3. **有效质量增强** 在 CDW 量子临界点附近显著
4. 自然解释铜氧化物相图: 强耦合 d-wave SC 出现在 charge-order QCP 附近
5. **AL 顶角修正是关键** — 传统 mean-field 近似忽略了这些
6. 方法可推广到多轨道 Hubbard 模型 (铁基、镍基)

## 精确数值摘录
- 具体 Tc 增强因子需查正文 (仅获取摘要)
- 方格子 Hubbard 模型参数

## 与已有工作的区别
- 传统 FLEX 只考虑 RPA 级别，忽略 AL 顶角修正
- Yamase (2023, 上面一篇) 发现 SF 有相位挫败问题 — 本文的 CDW 涨落提供了解决方案
- 守恒近似保证了物理一致性

## 启发的新想法
**假设:** CDW 涨落作为额外配对通道可能适用于 nickelate — La₃Ni₂O₇ 在常压下确实有 charge/spin density wave order。如果 CDW QCP 在压力下恰好位于超导 dome 附近，这可以解释为什么 SC 只在特定压力范围出现。

**更深层:** 如果 charge fluctuation 的 AL 顶角修正是高 Tc 的必要成分，那么我们的 TCE 模型可能需要第三个通道: phonon + SF + CDW fluctuation → "Three-Channel Eliashberg"。

## 与研究的关联
★★★ **直接挑战和补充我们的 TCE 框架:**
1. 如果 CDW 涨落是高 Tc 的必要条件，简单的 phonon + SF 双通道可能永远不够
2. 这解释了为什么 Night 31 的 TCE score 降到 32/100 — 我们可能遗漏了 charge channel
3. **行动项:** 在 TCE 模型中加入 Aslamazov-Larkin 型 charge channel
