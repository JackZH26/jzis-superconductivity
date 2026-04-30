# Wang et al. — Discovery of High-Temperature Superconducting Ternary Hydrides via Deep Learning

**arXiv:** 2502.16558 | **Year:** 2025
**Authors:** Wang, Zhang, Wang, Liu, Lv, Wang, E, Ma

## 核心结果

用深度学习框架大规模搜索三元超氢化物：
- **搜索空间**: 29 元素组合，~3600 万三元氢化物结构
- **发现**: 144 个潜在高温超导体，预测 Tc > 200 K，热力学稳定（@ 200 GPa）
- **其中 129 个全新**: 跨越 27 种新结构原型，此前从未报道
- **框架组成**: 高通量晶体结构搜索 + 物理约束筛选 + Tc 精确预测

## 关键方法

1. **深度学习 Tc 预测模型**: 训练于已知超导氢化物数据
2. **高通量晶体结构探索**: 结合进化算法 + 随机结构搜索
3. **物理筛选**: 热力学稳定性（convex hull）+ 动力学稳定性（phonon）+ Eliashberg Tc

## 与研究的关联

**★ 直接可用于 MSc₂H₂₄ 家族搜索:**
- 144 个候选中是否有 MSc₂H₂₄ 型结构？需查原文 supplementary
- 29 元素包含 La, Sc, Ce, Y 吗？如果是，应已覆盖我们关注的体系
- 框架中的 Tc 预测可能没考虑 anharmonic 修正（Type I/II 效应）

**关键数值:**
- 144 candidates with Tc > 200 K @ 200 GPa [来源: abstract, 2502.16558]
- 129 novel compounds, 27 new prototypes [来源: abstract, 2502.16558]
- Search space: ~36 million structures [来源: abstract, 2502.16558]

## 启发的新想法

1. **[可验证]** 在 144 个候选中检索 MSc₂H₂₄ (M=La,Ce,Y,Ca) 结构——如果存在，可直接获取其 harmonic Tc 估算
2. **[关键限制]** DL 预测基于 harmonic Eliashberg → 如果 Type I anharmonic 效应使 λ 降低 30%，实际 Tc 可能显著低于预测
3. **[策略]** 对 DL 预测的 top 候选应用我们的 iCOBI descriptor 进行 Type I/II 分类，优先验证 Type II（λ 可能增加）的候选
